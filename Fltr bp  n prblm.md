Fltr bp  n prblm





Extr fun  enhance rdable


body: Column(
  children: [
    _isLoading
        ? Center(child: CircularProgressIndicator())
        : buildListView(),
    buildElevatedButton(),
  ],




ElevatedButton buildElevatedButton() {
  return ElevatedButton(
          onPressed: () {
            // 按钮点击事件
            runApp(SecondPage());
          },
          child: Text('goto form'),
        );
}


Goto anothe page  runApp()

ElevatedButton buildElevatedButton() {
  return ElevatedButton(
          onPressed: () {
            // 按钮点击事件
            runApp(SecondPage());
          },
          child: Text('goto form'),
        );
}


Form list page
C:\0prj\paymentJava2024\lib\list.dart


Ajax http api


// final response = await http.get(Uri.parse('https://example.com/users')); // 替换为你的 AJAX URL

// if (response.statusCode == 200) {


Ui 控件大概20个
布局控件 。。。输入form控件。。。展示list控件。
Ui控件 四大类型


Flutter 提供了丰富的控件库，以下是一些常见的控件及其简要描述：
1. Container
用于创建一个矩形视觉元素，可以包含其他控件，支持装饰、边距、填充等属性。
2. Column 和 Row
Column: 垂直布局的控件，可以包含多个子控件。
Row: 水平布局的控件，可以包含多个子控件。
3. Stack
允许控件重叠，后面的控件会在前面的控件下方。
4. ListView
可滚动的列表，用于显示大量数据。支持水平和垂直方向。
5. GridView
网格布局的滚动列表，适合显示类似网格的数据。
6. Text
显示文本的控件，支持样式设置，如字体大小、颜色等。
7. Image
用于显示图像，支持本地和网络图像。
8. Button 系列
ElevatedButton: 带有阴影的按钮。
TextButton: 文字按钮，通常没有阴影。
OutlinedButton: 边框按钮。
9. TextField
输入文本的控件，支持多种输入类型和样式。
10. Checkbox 和 Radio
Checkbox: 复选框，允许用户选择多个选项。
Radio: 单选按钮，只能选择一个选项。
11. Switch
开关控件，用户可以在开/关状态之间切换。
12. AppBar
应用的顶部导航栏，通常包含标题和操作按钮。
13. Drawer
侧边导航栏，可以通过滑动或点击图标打开。
14. Snackbar
用于显示短暂的信息提示，通常在底部显示。
15. Dialog
弹出对话框，用于显示信息或询问用户操作。
16. BottomNavigationBar
底部导航栏，适用于多页面应用。
17. Form
表单控件，结合 TextFormField 和其他输入控件使用。
18. FutureBuilder 和 StreamBuilder
用于异步操作的控件，自动重建 UI 根据未来的结果或流的更新。
19. GestureDetector
用于识别用户的手势（点击、双击、滑动等）。
20. CustomPainter
自定义绘制控件，可以根据需要绘制复杂的图形。
这些控件可以组合使用，创建出丰富多彩的用户界面。根据应用的需求选择合适的控件，可以大大提高开发效率。

