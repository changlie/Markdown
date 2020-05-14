### 一、原生方式
#### 语法格式
```
|项目|价格|数量|
|:---|---:|:---:|
|iPhone|6000元  |3  |
|iPad  |3000元  |4  |
|iMac  |10000元 |5  |
```
可简化，取消行两侧管道符号"|"

```
项目|价格|数量
:-|-:|:-:
iPhone|6000元  |3  
iPad  |3000元  |4  
iMac  |10000元 |5  
```
#### 语法说明
```
不管是哪种方式，第一行为表头，第二行分隔表头和主体部分，第三行开始每一行代表一个表格行；
分隔表头“-”至少有一个
列与列之间用管道符号 “|” 隔开，原生方式的表格每一行的两边也要有管道符。
可在第二行指定不同列单元格内容的对齐方式，默认为左对齐，在 “-” 右边加上 “:” 为右对齐，在 “-” 两侧同时加上 “:” 为居中对齐。
```
表现
项目|价格|数量
:-|-:|:-:
iPhone|6000元  |3  
iPad  |3000元  |4  
iMac  |10000元 |5  

### 二、利用HTML<table>标签
表现丰富
列宽 width=20%	表头居中 style="text-align:center"	居右	列3
设置背景色	bgcolor=rgb(92, 184, 92)	bgcolor=#eea236	bgcolor=pink
合并列	起始列colspan=2 align=center
合并行
起始行rowspan=3	align=center对th无效	cell	cell
style="text-align:right"	cell	合并行 rowspan=2
cell	cell
cell	cell	cell	cell
可设置列宽（通过th、td均可以设置）、单元格背景色、合并列、合并行。
代码展示
```html
<table>
   <tr>
        <th width=20%>列宽 `width=20%`</th>
        <th width=45% style="text-align:center">表头居中 `style="text-align:center"`</th>
        <th widht=20% style="text-align:right">居右</th>
        <th widht=5%>列3</th>
   </tr>
   <tr>
        <td >设置背景色 </td>
        <td bgcolor=rgb(92, 184, 92)>`bgcolor=rgb(92, 184, 92)`</td>
        <td bgcolor=#eea236>`bgcolor=#eea236`</td>
        <td bgcolor=pink>`bgcolor=pink`</td>
   </tr>
   <tr>
        <td>**合并列**</td>
        <td colspan=3 align=center> `起始列colspan=2` `align=center`</td>
   </tr>
   <tr>
        <td rowspan=3>**合并行** <br>`起始行rowspan=3`</td>
        <td align=center>`align=center`对`th`无效</td>
        <td>cell</td>
        <td>cell</td>
   </tr>
   <tr>
        <td style="text-align:right">`style="text-align:right"`</td>
        <td>cell</td>
        <td rowspan=2>合并行 `rowspan=2`</td>
   </tr>
   <tr>
        <td>cell</td>
        <td>cell</td>
   </tr>
   <tr><td>cell</td><td>cell</td><td>cell</td><td>cell</td></tr>
</table>
```
