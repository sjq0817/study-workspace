#### 表格的基本使用
+ 表格标签
```<table>、<tr>、<td>```
+ table 表格 
+ tr table row 表格行
+ td table data 表格数据
```
<table>
    <tr>
        <td>
        </td>
    </tr>
</table>
```
####  table的border属性
+ 为了让表格能够显示边框，table标签通常又border属性
```
<table border="1">
    ...
</table>
```
#### table的caption属性
+ caption是表格的标题，他常常作为table的第一个子元素出现
```
<table border="1">
    <caption>我是表格的标题</caption>
    <tr>
        <td>
        </td>
    </tr>
</table>
```

#### ```<th>```标签
+ th是“标题小格”，可以代替td的作用，表示标题小格
```
<table>
    <tr>
        <th>
        </th>
    </tr>
</table>
```
#### 复杂表格
#### 单元格的合并
+ colspan属性
    + colspan属性用来设置td或者th的列跨度
    + rowspan属性用来设置td或th的行跨度
    + 同时有colspan、rowspan


#### 表格其他特性
+ thead标签定义表头
+ tbody标签定义表核心内容
+ tfoot标签定义表脚，通常是汇总行
#### cellspacing、cellpadding属性
+ cellpadding属性定义了表格单元的内容和边框之间的空间，已经废弃，使用CSS代替
+ cellspacing属性定义了两个单元格之间空间的大小，已经废弃，使用CSS代替