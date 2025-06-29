Es dsl 的查询总结
Es dsl与sql和普通3gl的常用查询语句基本一一对应。可以互相翻译使用，方便简化验证。
Es dsl也与lucene查询语法几乎一致，方便本地验证使用。。
3gl就是常见的js java这类语言
4gl包括 sql和es dsl
5gl 即是自然语言，这里采用受限自然语言，更加精确描述程序操作，使其可以直接一比一翻译为其他程序语言。调用细节使用js java类似括号语法。。如果实现其解析器，也可以直接执行获取查询结果。。

常见的查询 统计 分析聚合语法对应总结如下。。




=====数据检索
单条件查询
受限自然语言： 查询集合(users, 搜索条件( 字段(id, 等于(1))));

Sql语法 select * from users where id=1

Es的语法query

Elasticsearch 的查询 DSL，可以这样编写：
 GET /users/_search
{
  "query": {
    "term": {
      "id": 1
    }
  }
}


3GL语言fliter函数 Ts/Js 语法   java等


 // 示例数据
const users = [
    { id: 1, name: "Alice", age: 30 },
    { id: 2, name: "Bob", age: 25 },
 
];

// 根据 id 查询用户
const result = users.filter(user => user.id === 1);


多条件and查询
受限自然语言：：查询集合(users, 搜索条件(并列条件(字段(id, 等于(2)), 字段(age, 等于(25)))));


Es dsl。。。Query 配合must

Elasticsearch DSL 查询
 GET /users/_search


{
  "query": {
    "bool": {
      "must": [
        {
          "term": {
            "id": 2
          }
        },
        {
          "term": {
            "age": 25
          }
        }
      ]
    }
  }
}
Sql语法SELECT * FROM users WHERE id = 2 AND age = 25;
3gl程序语言语法 filter函数
// 示例数据
const users = [
    { id: 1, name: "Alice", age: 30 },
    { id: 2, name: "Bob", age: 25 },
    { id: 3, name: "Carol", age: 27 },
    { id: 2, name: "David", age: 25 },
    { id: 4, name: "Eve", age: 28 },
];

// 根据 id 和 age 查询用户
const result = users.filter(user => user.id === 2 && user.age === 25);
 模糊查询
自然语言  查询集合(users, 搜索条件( 字段(name, 包含("ali"))));

Sql     SELECT * FROM users WHERE name LIKE '%ali%';
Es  使用query wildcard
 GET /users/_search

{
  "query": {
    "wildcard": {
      "name": "*ali*"
    }
  }
}


 子查询和派生表
. 公共表达式（CTE）
集合操作 UNION /INTERSECT  EXCEPT
. 数据取样。。随机数据抽取查询
数据转换
====数据分析 统计 聚合计算

简单聚合查询   count()
长度（）
程序模式  arr. length函数
const users = [
  { id: 1, name: "Alice", age: 30 },
  { id: 2, name: "Bob", age: 25 },
  { id: 3, name: "Carol", age: 27 },
  { id: 4, name: "David", age: 35 },
  { id: 5, name: "Eve", age: 28 }
];

// 模拟 SQL 查询：SELECT COUNT(*) AS 总数 FROM user
const totalCount = users.length;


Sql  select count(*) as 总数 from user
和es dsl

{
  "query": {
    "match_all": {}
  },
  "aggs": {
    "total_count": {
      "value_count": {
        "field": "id"
      }
    }
  }
}

聚合计算sum（）
聚合(users,总和(age,"totalAge"),总和(id,"totalID")));
程序语言，使用reduce函数聚合

const users = [
  { id: 1, name: "Alice", age: 30 },
  { id: 2, name: "Bob", age: 25 },
  { id: 3, name: "Carol", age: 27 },
  { id: 4, name: "David", age: 35 },
  { id: 5, name: "Eve", age: 28 }
];

// 模拟 SQL 查询：SELECT SUM(age) AS 总数 FROM user
const totalAge = users.reduce((sum, user) => sum + user.age, 0);

select sum(age)   from user
Es dsl

{
  "query": {
    "match_all": {}
  },
  "aggs": {
    "total_age": {
      "sum": {
        "field": "age"
      }
    }
  }
}


复杂聚合计算,分组聚合 gropuby

自然语言   分组汇总(users,汇总列(总数("total")),分组列(sex)));

分组汇总(users,汇总列(总和(age,"totalAge")),分组列(sex)));

select count(*) total，sex  from user groupby sex
3gl  还是reduce复杂版

const users = [
    { id: 1, name: "Alice", age: 30, sex: "female" },
    { id: 2, name: "Bob", age: 25, sex: "male" },
    { id: 3, name: "Carol", age: 27, sex: "female" },
    { id: 4, name: "David", age: 35, sex: "male" },
    { id: 5, name: "Eve", age: 28, sex: "female" },
];

// 使用 reduce 分组统计性别人数
let callbackfn = (acc, user) => {
    // 如果性别已经存在，则加1；如果不存在，则初始化为1
    acc[user.sex] = (acc[user.sex] || 0) + 1;
    return acc;
};
// reduce(fun,iniVal)
const genderCount = users.reduce(callbackfn, {});

console.log(genderCount);
//{ female: 3, male: 2 }


Dsl es

{
  "size": 0, 
  "aggs": {
    "group_by_sex": {
      "terms": {
        "field": "sex.keyword", 
        "size": 10
      },
      "aggs": {
        "sex_count": {
          "value_count": {
            "field": "sex.keyword"
          }
        }
      }
    }
  }
}


====翻页与排序
NL    截取(offset, offset + limit);

3gl程序语言语法   subarr模式 截取数组

const users = [
  { id: 1, name: "Alice", age: 30 },
  { id: 2, name: "Bob", age: 25 },

// LIMIT 和 OFFSET
const offset = 5555; // 从第 5556 条开始
const limit = 999;   // 返回 999 条数据

const result = sortedUsers.slice(offset, offset + limit);

Sql语法  SELECT * FROM users ORDER BY id LIMIT 999 OFFSET 5555
Es dsl
{
  "query": {
    "match_all": {}
  },
  "sort": [
    {
      "id": {
        "order": "asc"
      }
    }
  ],
  "from": 5555,
  "size": 999
}

排序
NL  排序（）

程序语言语法 sort函数
// 按 id 升序排序 const sortedUsers = users.sort((a, b) => a.id - b.id);
Sql 和 es dsl


动态查询：
使用  遍历条件，将字段和值逐一匹配
动态排序字段： 如果需要根据动态字段排序，可以将字段名作为参数传递

附录

自然语言查询解析器（ js实现
全部实现其解析器大约需要200个函数

//qry.ts

import {等于, 大于, 字段, 并列条件, 搜索条件, 查询集合} from './qryNL';
const users = [
    {id: 1, name: "Alice", age: 30, sex: "female"},
    {id: 2, name: "Bob", age: 25, sex: "male"},
    {id: 3, name: "Carol", age: 27, sex: "female"},
    {id: 4, name: "David", age: 35, sex: "male"},
    {id: 5, name: "Eve", age: 28, sex: "female"},
];
let id = "id";
let age="age";let name="name";
var li = 查询集合(users, 搜索条件(并列条件(字段(id, 等于(2)), 字段(age, 等于(25)))));
console.log(li);


Ref
数据查询与分析常见操作总结  v2.docx
