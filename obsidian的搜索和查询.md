# 搜索和查询
> 搜索和查询是两个不同的概念

* 搜索：对**文本**进行某种特定的规则进行查找
* 查询：对**属性**进行某种特定的规则进行查找

## obsidian中的搜索
在obsidian插件外的搜索是只支持markdown格式来保存结果的

### 快捷键
在obsidian中，官方提供了搜索功能
	默认快捷键为：
	* **针对单个文本的：Ctrl + F**
	* 针对整个资料库的：**Ctrl/Cmd + Shift + F**
### 搜索面板
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202303261629343.png)
* 搜索技巧
	*  **直接搜索关键词**
	* **包含多个关键词（空格隔开）**
	* **包含某一个关键词（OR隔开）**
	* **不包括某个关键词（-隔开）**
	* **指定搜索范围**
		* 搜索文件名： file:word
		* 搜索文本内容： content:word
		* 搜索标签：tag:#word
		* 搜索同一行中的多个关键词：line:word1 word2
		* 搜索同一章节中的多个关键词：section:word1 word2
		* 搜索同一段落的多个关键词：block:word1 word2
	* **搜索任务**
		* 搜索任务：task:""
		* 搜索待完成任务：task-todo:""
		* 搜索已完成任务：task-done:""
### 保存查询结果
代码：query
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202303261631299.png)


---

## obsidian中*DataView*的查询


### DataView是什么？
DataView是**obsidian的一个插件**，它可以对obsidian进行**查询**

### DataView的原理
它的原理和**数据库**的原理如出一辙，可以说
> 这是你做笔记的一小步，确实你面向数据库开发的一大步

既然是查询数据库，那它的**查询对象和查询依据**是什么呢？
* 查询对象：Obsidian知识库
* 查询依据：YAML/Meatainfo
	* YAML：需要我们手动攥写的检索信息
	* Meatainfo：文件自带的检索信息

### 应用场景
什么时候用**搜索**？
	1. 条件单一
	2. 无需保存搜索结果
什么时候用**查询？**
	1. 条件复杂
	2. 需要保存搜索结果

### YAML
* YAML位于文章的开头
	* 首尾三个-
		![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202303261632759.png)

* obsidian支持的YAML字段
	* tags
	* publish
	* cssclass
	* aliases
	* 自定义字段  
		* category  
		* date  
		* time  
		* title  
		* rating  
	* 行内标记  
		* One Field:: Value  
		* 这份文档，可以打 [rating:: 5] 分  

### Obsidian文件属性  
* file.name: 文件标题(字符串)  
* file.folder: 文件所属文件夹路径  
* file.path: 文件路径  
* file.size: (in bytes) 文件大小  
* file.ctime: 文件的创建时间（包含日期和时间）  
* file.mtime: 文件的修改时间  
* file.cday: 文件创建的日期  
* file.mday: 文件修改的日期  
* file.tags: 笔记中所有标签数组  
* file.etags: 除去子标签的数组  
* file.inlinks: 指向此文件的所有传入链接的数组  
* file.outlinks: 此文件所有出站的链接数组  
* file.aliases: 文件别名数组  
* file.day：如果文件名中有日期，那么会以这个字段显示。比如文  
件名中包含 yyyy-mm-dd（年-月-日，例如2021-03-21），那么  
就会存在这个 metadata。  
* 任务属性  
Task 会继承所在文件的所有字段，比如 Task 所在的页面中已经包  
含了 rating 信息了，那么 task 也会有  
* completed: 任务是否完成  
fullyCompleted: 任务以及所有的子任务是否完成  
* text: 任务名  
* line: task 所在行  
* path: task 所在路径  
* section: 连接到任务所在区块  
* link: 连接到距离任务最近的可连接的区块  
* subtasks: 子任务  
* real: 如果为 true, 则是一个真正的任务，否则就是一个任务之前  
或之后的元素列表  
* completion: 任务完成的日期  
* due: 任务到期时间  
* created: 创建日期  
* annotated: 如果任务有自定义标记则为 True，否则为 False  
### DataView 使用  
* 展示方式
	* Table  
	* List  
	* Task  
* 语法  
	* dataview  
	* list|table|task  
	* from  
	* where  
	* sort  
	* asc，升序  
	* desc，降序  
* 查询方式  
	文件夹  
	标签  
	使用建议  
	保存常用查询  
	生成文件夹索引  
![](https://cdn.staticaly.com/gh/githubyuanjie/personal-photo-house@master/img/202303261632908.png)
