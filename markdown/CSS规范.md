md规范
==========================
常规格式规则
------------------------------

1.使用html5文档声明 `<!DOCTYPE html>`

2.HTML 的语义性 `<a href="recommendations/">All recommendations</a>`

3.多媒体元素降级处理
`<img src="spreadsheet.png" alt="Spreadsheet screenshot.">`

4.type属性

	不推荐的写法：`<link rel="stylesheet" href="//www.google.com/css/maia.css" type="text/css">`
	推荐的写法：`<link rel="stylesheet" href="//www.google.com/css/maia.css">`

5.使用二个空格缩进

6.只使用小写

css样式规则
------------------------------

1.css验证:[CSS验证](http://jigsaw.w3.org/css-validator/)

2.id和class名:使用富有含义和通用的id和class名,即使用功能性和通用性的命名方式减少文档或模板的不必要的改动

3.id和class的命名风格:id和class的命名在保持语义性的同时尽可能的短,可以缩写单词，但缩写后务必能让人明白其含义。比如author缩写成atr就非常费解

4.选择器:避免出现多余的祖先选择器,避免出现元素标签名作为选择器的一部分

	不推荐的写法：`ul#example {}` `div.error {}`
	推荐的写法：`#example {}` `.error {}`

5.前缀: 在大的项目（多人协作）中使用前缀可以减少样式冲突，同时可以明确选择器归属含义。

6.id和class名的分隔符:

	不推荐的写法：`.demoimage {} error_status{}`
	推荐的写法：`#video-id {} .ads-sample {}`

css格式规则
------------------------------

1.css属性按字母顺序书写

	`-moz-border-radius: 4px;`
	`-webkit-border-radius: 4px;`
	`border-radius: 4px;`
	