[toc]

## 1. 标题

```markdown
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

示例：

# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题



##  2. 段落和字体

### 2.1 段落

```markdown
这是第一段的内容 //添加两个空格
这是第二段的内容
```

```markdown
这是第一段的内容

这是第二段的内容
```

示例：

这是第一段的内容  
这是第二段的内容



这是第一段的内容

这是第二段的内容



### 2.2 字体

```markdown
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```

示例：

*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___



### 2.3 其他

```markdown
1. 分隔线
***
---
+++

2. 删除线
~~baidu~~

3. 下划线
<u>带下划线的文本</u>

4. 脚注
创建脚注格式[^Unilumin]
[^Unilumin]:LED行业领军品牌
```

示例：

1. 分隔线
***
---
+++

2. 删除线
~~baidu~~

3. 下划线
<u>带下划线的文本</u>

4. 脚注
创建脚注格式[^Unilumin]

[^Unilumin]:LED行业领军品牌



## 3. 列表

```markdown
1. 无序列表
* 第一项
+ 第二项
- 第三项

2. 有序列表
1. 第一项
2. 第二项
3. 第三项

3. 列表的嵌套
1. 第一项
	- 第一项嵌套的第一个元素
	- 第一项嵌套的第二个元素
2. 第二项
	- 第二项嵌套的第一个元素
	- 第二项嵌套的第二个元素
```

示例：

1. 无序列表
* 第一项
+ 第二项
- 第三项

2. 有序列表
1. 第一项
2. 第二项
3. 第三项

3. 列表的嵌套
1. 第一项
	- 第一项嵌套的第一个元素
	- 第一项嵌套的第二个元素
2. 第二项
	- 第二项嵌套的第一个元素
	- 第二项嵌套的第二个元素





## 4. MarkDown区块

```markdown
1. 区块
>区块引用
>>第一层嵌套
>>>第二层嵌套

2. 区块与列表混用
>区块中使用列表
>>1. 第一项
>>>- 第一项嵌套的第一个元素
>>>- 第一项嵌套的第二个元素
>>2. 第二项
>>>- 第二项嵌套的第一个元素
>>>- 第二项嵌套的第二个元素
```

示例：

1. 区块
>区块引用
>>第一层嵌套
>>
>>>第二层嵌套

2. 区块与列表混用
>区块中使用列表
>>1. 第一项
>>>- 第一项嵌套的第一个元素
>>>- 第一项嵌套的第二个元素
>>2. 第二项
>>>- 第二项嵌套的第一个元素
>>>- 第二项嵌套的第二个元素



## 5. 代码

```markdown
1. 单行使用
`代码`
2. 多行使用
​```
```

示例：

1. 单行使用
`代码`
2. 多行使用

```

```



## 6. 链接

```markdown
1. 常规方式
[链接名称](链接地址)
ex：[baidu](https://www.baidu.com)

2. 直接使用链接地址
<链接地址>
ex:<https://www.baidu.com>

3. 使用变量方式
[链接名称][变量x]
[变量x]:链接地址
ex:
[baidu][1]
[1]:https://www.baidu.com
```

示例：

1. 常规方式
[链接名称](链接地址)
ex：[baidu](https://www.baidu.com)

2. 直接使用链接地址
<链接地址>
ex:<https://www.baidu.com>

3. 使用变量方式
[链接名称][变量x]
[变量x]:链接地址
ex:
[baidu][1]

[1]:https://www.baidu.com



## 7. 图片

```markdown
1. 常规方式
![alt 属性文本](图片地址 "可选图片标题")
ex:
![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")

2. 使用变量方式
[图片名称][变量x]
[变量x]:图片地址
ex:
[RUNOOB][1]
[1]: http://static.runoob.com/images/runoob-logo.png

3. 使用html标签形式
<img src="http://static.runoob.com/images/runoob-logo.png" width="20%">
```

示例：

1. 常规方式
![alt 属性文本](图片地址 "可选图片标题")
ex:
![RUNOOB 图标](runoob-logo.png "RUNOOB")

2. 使用变量方式
[图片名称][变量x]
[变量x]:图片地址
ex:
[RUNOOB][1]
[1]: http://static.runoob.com/images/runoob-logo.png

3. 使用html标签形式
<img src="http://static.runoob.com/images/runoob-logo.png" width="20%">



## 8. 表格

```markdown
| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
```

示例：

| 左对齐 | 右对齐 | 居中对齐 |
| :----- | -----: | :------: |
| 单元格 | 单元格 |  单元格  |
| 单元格 | 单元格 |  单元格  |



## 9. 高级技巧

```
1. MarkDown支持的html标签
<kbd> <b> <i> <em> <sup> <sub> <br>等

2. 转义
**文本加粗** 
\*\* 正常显示星号 \*\*

3. 公式
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$
```

示例：

1. MarkDown支持的html标签
<kbd> <b> <i> <em> <sup> <sub> <br>等

2. 转义
**文本加粗** 
\*\* 正常显示星号 \*\*

3. 公式

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
${$tep1}{\style{visibility:hidden}{(x+1)(x+1)}}
$$