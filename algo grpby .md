


const users = [
{ id: 1, name: "Alice", age: 30, sex: "female" },
{ id: 2, name: "Bob", age: 25, sex: "male" },
{ id: 3, name: "Carol", age: 27, sex: "female" },
{ id: 4, name: "David", age: 35, sex: "male" },
{ id: 5, name: "Eve", age: 28, sex: "female" },
];

//select count(*) cnt,sex  from user groupby sex
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