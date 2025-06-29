布局算法 数组 网格化grpby算法


// 将按钮组织成一个二维数组，每行3个按钮
 var buttonRows = buttons .Select((button, index) => new { button, index }) .GroupBy(x => x.index / 3) 


可以设置这个grpby数学数字  rowidx=1  





.Select(g => g.Select(x => x.button).ToArray()) .ToArray();


然后从rowidx 循环 from 1....10
得到数据。。
