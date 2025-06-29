最简单dsl 实现  ui模板的格式与实现




最简单的 UI 模板语法通常会具有以下特性：
直观的占位符语法：用于将数据插入到模板中。
最少的逻辑处理：例如条件语句和循环，但不需要复杂的操作。
1. 基于占位符的模板 (纯文本模板)
使用 ${} 或 {{}} 作为占位符：
html
Copy code
<div>
  Hello, {{name}}!
  <ul>
    {{#each items}}
      <li>{{this}}</li>
    {{/each}}
  </ul></div>

解析工具（简易实现）：


function render(template, data) {
  return template.replace(/\{\{(.*?)\}\}/g, (match, key) => {
    let value = key.trim();
    if (value.startsWith("#each")) {
      const arrKey = value.split(" ")[1].trim();
      const arr = data[arrKey];
      const listItems = arr.map(item => template.match(/<li>(.*?)<\/li>/)[1].replace('{{this}}', item)).join('');
      return listItems;
    }
    return data[value] || '';
  });
}


3. Inline Template with Embedded Logic
逻辑由模板引擎内置支持，例如 Handlebars、EJS：
4. Pure HTML with data-bind
绑定逻辑通过属性而非语法完成，通常配合简单的框架（如 KnockoutJS 或 Vue）：
<div>
  <p>Hello, <span data-bind="name"></span>!</p>
  <ul>
    <li data-repeat="item in items">{{item}}</li>
  </ul


绑定工具：
javascript
Copy code
function bind(template, data) {
  template.querySelectorAll('[data-bind]').forEach(el => {
    const key = el.getAttribute('data-bind');
    el.textContent = data[key];
  });
  template.querySelectorAll('[data-repeat]').forEach(el => {
    const [item, arrKey] = el.getAttribute('data-repeat').split(' in ');
    const arr = data[arrKey.trim()];
    arr.forEach(value => {
      const clone = el.cloneNode(true);
      clone.textContent = value;
      el.parentElement.insertBefore(clone, el);
    });
    el.remove();
  });
  return template;
}


