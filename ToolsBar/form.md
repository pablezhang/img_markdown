<h1 style="text-align:center">表单配置文档</h1>
[TOC]
***
## 表单各控件通用API
此表格内属性适用于系统中所有的控件。具体用法也可直接查询[完整实例](#all_example)
|属性|	说明|	类型|	默认值|
|---|---|---|----|
|disabled|	控件禁用状态|	<font color='#c41d7f'> boolean</font>|	false
|readonly|	同为控件禁用状态|	<font color='#c41d7f'> boolean</font>|	false|
|visible|	是否显示控件|	<font color='#c41d7f'> boolean</font>|	true
|title|	控件的标题|	<font color='#c41d7f'> string</font>|	
|placeholder|	提示文案|	<font color='#c41d7f'> string</font>|	""
|minCol|	控件所占栅格列数|	<font color='#c41d7f'> number</font>|	4
|name|	控件名称|	<font color='#c41d7f'> string</font>|	-
|tag|	控件标签，通常用以规则中挑选指定控件|	<font color='#c41d7f'> string</font>|	
|required|	是否必填|	<font color='#c41d7f'> boolean</font>|	false
|regex|	校验规则，值为正则表达式|	<font color='#c41d7f'> string</font>|	
|maxLength|	允许输入内容最大长度|	<font color='#c41d7f'> number</font>	
|regexMsg|	控件校验失败时在控件下方的提示信息|	<font color='#c41d7f'> string</font>	
|dataSource|	用以为控件绑定数据源|	<font color='#c41d7f'> string</font>	
|alwaysReload| 易变数据源，用于从一直处于读写变化中的数据表中读取数据源的业务情形；<br/>效果是每次向服务端请求请求数据，而不从前端缓存中读取 | <font color='#c41d7f'> boolean</font> |	false



## 表单各控件Addins通用API
此表格内属性适用于系统中所有控件的`addins`属性。
|属性|	说明|	类型|	默认值|
|---|---|---|---|
|mgBtm|	主动指定控件下边距|	<font color='#c41d7f'> <font color='#c41d7f'> number</font></font>|	12
|fixedHeight|	主动指定控件固定高度|	<font color='#c41d7f'> <font color='#c41d7f'> number</font></font>|	32
|titleCol|	控件作为整体分为12列，文本部分所占列数，可选值为`0-11` `fix100`|	<font color='#c41d7f'>number \| 'fix100'</font>	|"fix100"
|controlCol|	控件作为整体分为12列，输入框部分所占列数，可选值为`0-11` `calc-100` | | "calc-100"
|titleWid|	文本部分所占固定宽度|	<font color='#c41d7f'> <font color='#c41d7f'> number</font></font>	
|controlWid|	控件部分所占固定宽度|	<font color='#c41d7f'> <font color='#c41d7f'> number</font></font>	|
|txtColor|	文本颜色|	<font color='#c41d7f'> string</font>|	“#15688c”
|txtLayout|	文本水平排版方式, 可选值为 `left` 'center` `right` | <font color='#c41d7f'>string</font> |	"left"
|txtSize|	文本部分字体大小	"12px" | <font color='#c41d7f'> string</font> | "16px" | "18px" | "20px" | "22px" | "24px" | |"26px" | "28px"	"14px"
|fontBold|	文本是否加粗|	<font color='#c41d7f'>boolean</font>|	false
|offset|向右偏移列数,可选值为数字`0-12`表单可能需要在左侧留白，有两种做法：1使用占位符。2设置向右偏移量。<br/>区别：如果你不需要打印表单，推荐使用向右偏移，更加便捷。如果你需要打印表单，请使用占位符，占位符会在打印时保留空白位置，而设置的偏移量在打印时不会保留左侧空白。|	<font color='#c41d7f'> <font color='#c41d7f'> number</font></font>	|0



##表单各控件独有API
| 控件名称                        | 属性                                                         | 说明                                                         | 类型                                                         | 默认值                                                       |
| ------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 按钮: button                    | icon                                                         | 按钮是否显示图标                                             | <font color='#c41d7f'> string</font>                         |                                                              |
| 按钮: button                    | styleType                                                    | 设置按钮类型，可选值为 `primary` `dashed` `danger`           | <font color='#c41d7f'> string</font>                         | `default`                                                    |
| 按钮: button                    | size                                                         | 设置按钮大小，可选值为 `small` `large` 或者不设              | <font color='#c41d7f'> string</font>                         | `default`                                                    |
| 文本: label                     | addins.indent                                                | 文本是否缩进两个字节                                         | <font color='#c41d7f'>boolean</font>                         | `false`                                                      |
| 输入框：input                   | addins.unit                                                  | 在输入框后方添加字符串吗，通常作为输入框的单位               | <font color='#c41d7f'> string</font>                         | `''`                                                         |
| 多选输入框组:<br/>checkboxgroup | addins.rowComposing                                          | 是否水平分布，`false`代表垂直分布                            | <font color='#c41d7f'>boolean</font>                         | `true`                                                       |
| 多选输入框组:<br/>checkboxgroup | addins.list                                                  | 为多选输入框组配置选项，接收数组类型                         | <font color='#c41d7f'>{ label: string \| number, value: string \| number }[]</font> | `null`                                                       |
| 单选输入框组:<br/>radiogroup    | addins.list                                                  | 为单选输入框组配置选项，接收数组类型                         | <font color='#c41d7f'>{ label: string \| number, value: string \| number }[]</font> | `null`                                                       |
| 单选输入框组:<br/>radiogroup    | addins.valueName                                             | 为单选输入框组配置选项，接收数组类型                         | <font color='#c41d7f'>{ label: string \| number, value: string \| number }[]</font> | `null`                                                       |
| 单选输入框组:<br/>radiogroup    | addins.labelName                                             | 为单选输入框组配置选项，接收数组类型                         | <font color='#c41d7f'>{ label: string \| number, value: string \| number }[]</font> | `null`                                                       |
| 日期选择控件:<br/> date         | addins.config                                                | 用以支持ant-design原生配置，值为字符型、布尔型均可直接配置。具体见[DatePicker-API](https://ant.design/components/date-picker-cn/#%E5%85%B1%E5%90%8C%E7%9A%84-API) |                                                              |                                                              |
| 子表单:<br/>form                | addins.bimid                                                 | 指定要打开的表单ID                                           | <font color='#c41d7f'> string</font>                         | `''`                                                         |
| 子表单:<br/>form                | addins.btmid                                                 | 指定要打开的表单模板ID                                       | <font color='#c41d7f'> string</font>                         | `''`                                                         |
| 子表单:<br/>form                | addins.formId                                                | 子表单ID                                                     | <font color='#c41d7f'> string</font>                         | `''`                                                         |
| 输入框:<br/>input               | addins.addonBefore在输入框尾部增加元素                       | addonBefore                                                  | <font color='#c41d7f'> string</font>                         |                                                              |
| 二维码控件:<br/>qrcode          | addins.fixedHeight                                           | 指定二维码尺寸大小                                           | <font color='#c41d7f'> number</font>                         | `100`                                                        |
| 二维码:<br/>qrcode              | simpleLayout                                                 | 水平排版方式，可选值为`default` `tac` `tar`                  | <font color='#c41d7f'>string</font>                          | `default`                                                    |
| 评分控件: <br/>rate             | count                                                        | 用几颗星来表示评分                                           | <font color='#c41d7f'> number</font>                         | `51                                                          |
| 评分控件: <br/>rate             | addins.allowHalf                                             | 是否允许半星评分                                             | <font color='#c41d7f'> boolean</font>                        | `false`                                                      |
| 下拉框: select                  | addins.showVlaue                                             | 下拉框label中显示value                                       | <font color='#c41d7f'> boolean</font>                        | `false`                                                      |
| 下拉框: select                  | addins.searchEnable                                          | 下拉框是否可以搜索                                           | <font color='#c41d7f'> boolean</font>                        | `false`                                                      |
| 下拉框: select                  | list                                                         | 下拉框要显示的数据，为数组形式                               | <font color='#c41d7f'> Array<string, string \| number></font> |                                                              |
| 下拉框: select                  | labelName                                                    | 下拉框指定要显示的字段，通常显示字段对应语义化中文           | <font color='#c41d7f'> string</font>                         | `label`                                                      |
| 下拉框: select                  | valueName                                                    | 下拉框指定不显示的字段，但通常作为id使用                     | <font color='#c41d7f'> string</font>                         | `value`                                                      |
| 进度条: slider                  | min                                                          | 进度条显示的最小值                                           | <font color='#c41d7f'> number</font>                         | `0`                                                          |
| 进度条: slider                  | max                                                          | 进度条显示的最大值                                           | <font color='#c41d7f'> number</font>                         | `100`                                                        |
| 副标题: subTitle                | styleType                                                    | 指定副标题显示何种样式，可选值为 `default` `arrow` `arrow2` `slant` | <font color='#c41d7f'> string</font>                         | `default`                                                    |
| 开关按钮: switch                | defaultChecked                                               | 默认是否选中，注意在数据库中将对应字段设计为数值型，0代表不选，1代表选中 | <font color='#c41d7f'> number </font>                        | `false`                                                      |
| 开关按钮: switch                | checkedChildren                                              | 选中时显示的文字                                             | <font color='#c41d7f'> string </font>                        | `是`                                                         |
| 开关按钮: switch                | unCheckedChildren                                            | 未选中时显示的文字                                           | <font color='#c41d7f'> string </font>                        | `否`                                                         |
| 多行输入框: textarea            | minRow                                                       | 指定多行输入框最小行数                                       | <font color='#c41d7f'> number</font>                         | `4`                                                          |
| 多行输入框: textarea            | maxRow                                                       | 指定多行输入框最大行数                                       | <font color='#c41d7f'> number</font>                         | `6`                                                          |
| 时间控件: date                  | addins.config                                                | 支持[ant-design日期控件API](https://ant.design/components/time-picker-cn/#API)，适用值为`string` `number` `boolean`型的所有配置 | object                                                       |                                                              |
| 上传控件: upload2               | addins.showUploadList                                        | 是否显示已上传文件列表                                       | boolean                                                      | `true`                                                       |
| 上传控件: upload2               | addins.multiple                                              | 是否允许一次性上传多个文件                                   | boolean                                                      | `true`                                                       |
| 上传控件: upload2               | addins.btnTitle                                              | 上传按钮显示的文字                                           | string                                                       | `上传`                                                       |
| 上传控件: upload2               | addins.pid                                                   | 指定讲文件上传到指定文件夹，`pid`对应文件夹节点`nid`         | string                                                       | 默认使用`bimid`作为指定文件夹，但是非业务型需要手动指定`pid`, 见[上传控件注意事项](#upload2_notice) |
| 上传控件: upload                | addins.config                                                | 支持[ant-design上传控件API](https://ant.design/components/upload-cn/#API)，适用值为`string` `number` `boolean`型的所有配置 | <font color='#c41d7f'>object</font>                          |                                                              |
| 旧版上传控件: upload            | addins.showUploadList                                        | 是否显示已上传文件列表                                       | <font color='#c41d7f'>boolean</font>                         | `true`                                                       |
| 旧版上传控件: upload            | addins.pid                                                   | 指定讲文件上传到指定文件夹，`pid`对应文件夹节点`nid`         | <font color='#c41d7f'>string </font>                         | 默认使用`bimid`作为指定文件夹，但是非业务型需要手动指定`pid`见[上传控件注意事项](#upload2_notice) |
|                                 | 旧版上传控件因为bug，涉及百度开源上传控件源码，暂时已在设计面板中隐藏 |                                                              |                                                              |                                                              |


##表格控件API
        定制系统中表格分为两种:
        • 第一种为纯展示作用的的`展示表格`。通过绑定数据源展示数据。展示表格不可编辑。
        • 第二种为`主表表格`，作为多行数据表的导航来使用。主表表格具有可编辑特点。

| 属性                   | 说明                                                         | 类型                                                         | 默认值  |
| ---------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------- |
| dataSource             | 展示表格需要绑定的数据源名称字符串，需要在数据源面板中配合设计对应数据源 | <font color='#c41d7f'> string</font>                         | ''      |
| addins.isMain          | 是否开启主表表格                                             | <font color='#c41d7f'> boolean</font>                        | `false` |
| addins.indexKey        | 主表表格主键                                                 | <font color='#c41d7f'> string</font>                         | `iid`   |
| addins.hideOperatorBtn | 是否隐藏增加、删除操作按钮，可取值范围为`true` `false` `add` `delete` `add\|delete` | <font color='#c41d7f'>  <font color='#c41d7f'> boolean</font>\|string</font> | `false` |
| addins.columns         | 展示表格与主表表格的列配置，具体参见下方[columns](#columns)配置 |                                                              |         |
| addins.pagination      | 表格是否分页                                                 | <font color='#c41d7f'> boolean</font>                        | `false` |
| addins.bordered        | 表格是否显示边框                                             | <font color='#c41d7f'> boolean</font>                        | `true`  |
| addins.checkboxable    | 能否多选。设计之初用来在UI上标记行多选，使用后发现：主表只能同时编辑一条数据，<br>而行选中需求为用数组库字段加复选框形式处理。所以这个功能暂无用处） | <font color='#c41d7f'> boolean</font>                        | `true`  |
|addins.paginationType| 分页类型：前端分页、后台分页两种，前端分页默认每页`10`条，暂无定制每页数量功能。<br/>后台分页功能需配合规则使用，可选值为`fore \| server ` |<font color='#c41d7f'> string</font> | `fore`
|addins.editable| 表格能否编辑。目前业务逻辑中，主表表格自动为可编辑，非主表表格不可编辑。|<font color='#c41d7f'> boolean</font> | 同步`addins.isMain`|
|addins.maxHeight| 指定子表单的最大高度|<font color='#c41d7f'> number</font> | | 
|addins.config| 用以支持[Ant-design原生配置](https://ant.design/components/table-cn/#API)，举个&nbsp;<i class="icon-lemon" style="color: orange"></i>&nbsp;，怎么使用`Ant-design`的[横向滚动条](#x-scroll)|<font color='#c41d7f'> object</font> | | 

***
<h3 id="x-scroll" align="center">表格配置横向滚动条示例</h3>

```
"addins": {
    "config": {
        "className": "formScroll--noWrap",
        //设置横向或纵向滚动，也可用于指定滚动区域的宽和高，建议为 x 设置一个数字，如果要设置为 true，需要配合样式，如上放这个formScroll-noWarp制定了单元格不允许换行
        //注意这里的scroll会强制显示横线滚动条，即便表格内容宽度不超过x，也会出现
        "scroll": {    。
            "x": 1900,
            "y": 500
        }
    },
    "columns": [
        {
            "dataIndex": "xkssd",
            "key": "xkssd",
            "type": "select",
            "title": "开始时段",
            "dataSource": "开始时段",
            "width": "130px"
        },
        {
            "dataIndex": "xjssd",
            "key": "xjssd",
            "type": "select",
            "title": "结束时段",
            "dataSource": "结束时段",
            "width": "130px"
        },
        {
            "dataIndex": "xmmc",
            "key": "xmmc",
            "type": "input",
            "title": "项目名称",
            "width": "600px"
        },
        {
            "dataIndex": "gs",
            "key": "gs",
            "type": "input",
            "title": "工作工时",
            "width": "150px"
        },
        {
            "dataIndex": "jbgs",
            "key": "jbgs",
            "type": "input",
            "title": "加班工时",
            "width": "150px"
        },
        {
            "dataIndex": "wcqkjlpj",
            "key": "wcqkjlpj",
            "type": "select",
            "title": "经理评价",
            "visible": true,
            "dataSource": "经理评价",
            "width": "150px"
        },
        {
            "dataIndex": "pfz",
            "key": "pfz",
            "type": "input",
            "title": "任务得分",
            "width": "150px"
        },
        {
            "dataIndex": "zrr",
            "key": "zrr",
            "type": "input",
            "title": "日报填写人"
        }
    ],
    "layout": "hideTitle",
    "isMain": true,
    "addSort": "asc",
    "pagination": true,
    "hideOperatorBtn": true
},
```

### 目前主表表格单元格支持的控件类型
| 类型          | 说明         | config字段支持                                               | 特殊配置                                                |
| ------------- | ------------ | ------------------------------------------------------------ | ------------------------------------------------------- |
| \__index__    | 序号         | 不支持                                                       | 无                                                      |
| date          | 日期控件     | 支持[Ant-design Date配置](https://ant.design/components/date-picker-cn/#API) |                                                         |
| time          | 时间控件     | 支持[Ant-design Time配置](https://ant.design/components/time-picker-cn/#API) |                                                         |
| select        | 下拉框控件   | 支持[Ant-design Select配置](https://ant.design/components/select-cn/#Select-props) | `valueName` `labelName` 参见下方[例子](#table_examples) |
| link          | 超链接控件   | 不支持                                                       |                                                         |
| img           | 图片控件     | 不支持                                                       |                                                         |
| button        | 按钮控件     | 不支持                                                       |                                                         |
| upload        | 上传控件     | 支持[Ant-design Upload配置](https://ant.design/components/upload-cn/#API) |                                                         |
| file          | 文件控件     | 不支持                                                       |                                                         |
| qrcode        | 二维码控件   | 不支持                                                       |                                                         |
| file          | 文件控件     | 不支持                                                       |                                                         |
| radioGroup    | 单选框组     | 不支持                                                       |                                                         |
| checkboxGroup | 复选框组     | 不支持                                                       |                                                         |
| checkbox      | 复选框       | 不支持                                                       |                                                         |
| text          | 文本型(默认) | 不支持                                                       |                                                         |

***
Quicker

<h2 id="columns">表格控件columns配置</h2>
columns决定了表格的每一列以何种控件显示，其中`type`键值对决定了显示的控件类型，属于系统扩展字段。除了下方所列的三种配置，columns也支持[Ant-design原生columns配置](https://ant.design/components/table-cn/#Column)，如`align` `width` `children`等，这三种分别用来指定单元格文本水平排版方向、指定列宽度、表头分组三种功能。在下方给出了这[三种实例](#columns_example)，完整配置参见[Ant-design原生columns配置](https://ant.design/components/table-cn/#Column)。
PS：由于源码编辑器只支持简单值编辑，只用使用值为简单值的属性配置，而那些使用`ReactNode` `function`作为值的属性目前无法使用，若需使用，请扩展其功能。
| 属性                                                         | 说明                                                         | 类型                                 | 默认值 |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------ | ------ |
| dataIndex                                                    | 对应数据库字段名称.对于某些不存在的字段名称的列，例如按钮这种控件，<br/>可以写一个与其它`dataIndex`不重复的`string` | <font color='#c41d7f'> string</font> |        |
| title                                                        | 列的表头名称                                                 | <font color='#c41d7f'> string</font> | `''`   |
| type                                                         | 在单元格内设置不同类型的控件，可选值为`__index__` `date` `time` `select` `link` <br/>`img` `button` `upload` `file` `qrcode` `radioGroup` `checkboxGroup` `text` | <font color='#c41d7f'> string</font> | `text` |
| [Ant-design原生columns配置](https://ant.design/components/table-cn/#Column) |                                                              |                                      |        |


<h3 id="columns_examples"> columns表格配置例子 </h3>

```
"addins": {
    "columns": [
        {
        //通常对应数据表中的字段，但是如果你不需要保存该列数据，可以随便起个名字。适用于按钮、序号
            "dataIndex": "anyword", 
            "type": "__index__",
            "title": "序号",
        },
        {
            "dataIndex": "ywh", 
             "title": "业务号",
             "width": 100, // 指定列宽度，可以是number string类型
             "align": "center", // 指定列文本水平对齐方式，可选取值为left、center、right，默认center
             "children": [ // 用以分组
                {
                    "dataIndex": "ywh", 
                     "title": "单号",
                     "align": "center",
                     "width": 50
                },
                {
                    "dataIndex": "ywh", 
                    "title": "双号",
                    "align": "center",
                    "width": 50
                }
             ]
        }
    ]
}
```


<h3 id="table_examples"> 主表表格配置例子 </h3>
```javascript

 {
        "type": "table",
        "title": "表格",
        "minCol": 12,
        "addins": {
            "columns": [
                {
                //通常对应数据表中的字段，但是如果你不需要保存该列数据，可以随便起个名字。适用于按钮、序号
                    "dataIndex": "anyword", 
                    "type": "__index__",
                    "title": "序号",
                },
                {
                    "dataIndex": "ywh", //默认字符型，可编辑
                    "disabled": true, // 禁用某一个列，以只读方式显示
                    "title": "业务号"
                },
                {
                    "dataIndex": "qlrmc",
                    "visible": false, //隐藏某一列
                    "title": "权利人"
                },
                {
                    "dataIndex": "ywh2", //默认字符型，可编辑
                    "title": "办理日期",
                    "type": "date",
                    "config": {
                        // antd 原生配置
                    }
                },
                {
                    "dataIndex": "ywh3", //默认字符型，可编辑
                    "title": "办理时间",
                    "type": "time",
                    "config": {
                        // antd 原生配置
                    }
                },
                {
                    "dataIndex": "lzrxm",
                    "title": "领证人",
                    "type": "select",
                    "dataSource": "组织机构", // 在数据源中定义的数据源
                    "labelName": "organizationName", // 作用同普通下拉框控件一致，指定在下拉框中显示的名称
                    "valueName": "organizationId"// 作用同普通下拉框控件一致，指定在下拉框中显示的名称
                },
                {
                    "dataIndex": "fzsj",
                    "title": "证书预览",
                    "type": "link"
                },
                {
                    "dataIndex": "lzfs",
                    "title": "下载",
                    "type": "button"
                },
                {
                    "dataIndex": "lzfs2",
                    "title": "上传",
                    "type": "upload",
                    "btnTitle": "上传附件", // 这里决定上传按钮的会显示上传按钮的按钮名称
                    "pid": "BM0000001", // 上传到目标文件夹的nid，流程视图默认使用业务id作为文件夹的pid，非流程视图需要指定pid
                    "showUploadList": false, // 是否显示上传文件里列表
                    "multiple": false, // 是否允许一次性上传多个文件
                    "config": {
                        // antd 原生组件配置
                    }
                },
                {
                    "dataIndex": "lzfs23",
                    "title": "资料",
                    "type": "file"
                },
                {
                    "dataIndex": "lzfs5",
                    "title": "资料",
                    "type": "qrcode"
                },
                {
                    "dataIndex": "lzfs5",
                    "title": "复选框组",
                    "type": "checkboxGroup",
                    "options": [
                        {
                            "label": "A",
                            "value": "a"
                        },
                        {
                            "label": "B",
                            "value": "b"
                        }
                    ]
                },
                {
                    "dataIndex": "lzfs6",
                    "title": "单选框组",
                    "type": "radioGroup",
                    "options": [
                        {
                            "label": "C",
                            "value": "c"
                        },
                        {
                            "label": "D",
                            "value": "d"
                        }
                    ]
                },
                {
                    "dataIndex": "lzfs7",
                    "title": "复选框",
                    "type": "checkbox",
                    "options": [
                        {
                            "label": "C",
                            "value": "c"
                        },
                        {
                            "label": "D",
                            "value": "d"
                        }
                    ]
                },

            ],
            "layout": "hideTitle",
            "alwaysReload": true,
            "isMain": true,
            "pagination": true,
            "bordered": true,
            "editable": true,
            "hideOperatorBtn": true
        },
```

***

<h2 align="center" id="all_example"> 各控件用法实例及注意事项</h2>

<b>按钮控件:button</b>
注意事项: 按钮控件通常用来触发点击事件，而不用编辑内容保存到数据库中。因此不用为按钮指定字段，使用系统自动生成`name`即可。
```
{
    "type": "button",
    "title": "按钮",
    "styleType": "default", // 还有primary、dashed、danger三种风格的按钮，样式与antd一致
    "id": "control_button_v5a8qy11jgb0",
    "name": "control_button_v5a8qy11jgb0"
},
```
<b>复选框控件：checkbox</b>
注意事项: 需要使用复选框控件时，如果需要记录选中状态，即数据库字段保存选中与否。此时需要将对应数据库字段设计为`number`类型，使用过程中常见错误用法为将字段设计为`string`类型，这会导致复选框一致处于勾选状态。
```
{
    "type": "checkbox",
    "title": "复选框",
    "id": "control_checkbox_z0sag5e6a3iu",
    "name": "control_checkbox_z0sag5e6a3iu"
},
```
<b>复选框组控件: checkboxgroup</b>
注意事项: 1、数据库字段需要设计为`string`类型。 2、`list`为数组格式，其填充项遵从`lable` `value`为键名的格式，后期可根据需要扩展，开发人员参照`selectField`源码。
```
{
    "type": "checkboxgroup",
    "title": "复选框组",
    "minCol": 6,
    "valueName": "value",
    "addins": {
        "list": [// 这个list需要下方这种数组结构，如需动态配置，使用规则。如需定制字段名称，需要扩展功能。
            {
                "label": "Apple",
                "value": "Apple"
            },
            {
                "label": "Pear",
                "value": "Pear"
            },
            {
                "label": "Orange",
                "value": "Orange"
            }
        ]
    },
    "id": "control_checkboxgroup_a68vi831k4pt",
    "name": "control_checkboxgroup_a68vi831k4pt"
}
```
<b>日期控件: date</b>
注意事项: 无特别要求。如需要扩展一些特殊功能，可以参考[ant-desing文档]()，可支持其提供的所有功能。由于代码编辑器只能编辑简单数据类型，所以，只能注入属性值为简单数据类型的属性。简单值：`string` `boolean`  `number`
```
{
    "type": "date",
    "title": "选择日期",
    "id": "control_date_c71nvk3k3nrw",
    "name": "control_date_c71nvk3k3nrw"
    "config": {
        // antd 原生配置
    }
}
```
<b>日期范围控件: daterange</b>
```
{
    "type": "daterange",
    "title": "日期范围",
    "id": "control_daterange_seskgdfk8e76",
    "name": "control_daterange_seskgdfk8e76"
}
```
<b id="file">文件控件: file</b>
注意事项：该控件用来展示已上传文件，在配置时与普通输入框控件无任何差别。常见用法是通过规则中的setValue来实现，保存文件节点信息。建议使用该控件时将字段大小根据需要设置的相对大一些。另一点，储存在数据库中的值为JSON字符串，其`JSON.parse`解析后为`FileNode`组成的数组，使用时请注意这一点
```typescript
interface FileNode {
    ext: string //文件扩展名
    nid: string //文件id，唯一
    contentType: string  //文件类型
    fullName: string, //文件全称
}
```
```
{
    "type": "file",
    "title": "文件",
    "minCol": 12,
    "id": "control_file_i7ru1aq0v7dy",
    "name": "control_file_i7ru1aq0v7dy"
}
```
<b id="form">子表单控件: form
注意事项: 子表单控件需要一个`formId`才能正确加载。PS: 在设计业务由于业务模板设计时，子表单与主表单必须在同一个业务模板下，才会加载成功。
```
{
    "type": "form",
    "title": "子表单",
    "maxHeight": 200,
    "minCol": 12,
    "formId": "FM0000000001",
    "id": "control_form_a8ao4o6vzi2t",
    "name": "control_form_a8ao4o6vzi2t"
}
```
<b>分割线控件: hr</b>
注意事项:控件title会作为分割线显示内容。
```
{
    "type": "hr",
    "title": "分割线",
    "minCol": 12,
    "id": "control_hr_aa26jgqmvmd0",
    "name": "control_hr_aa26jgqmvmd0"
}
```
<b>图片控件: image </b>
注意事项：控件`value`值才是图片的`src`路径，也就是说`value`值必须为合法`src`路径。
```
{
    "type": "image",
    "title": "图片",
    "minCol": 12,
    "id": "control_image_bzfz5k0fswxr",
    "name": "control_image_bzfz5k0fswxr"
}
```
<b>输入框控件: input</b>
注意事项: 最为普通的控件，保持`name`与数据字段对应即可。
```
{
    "type": "input",
    "title": "业务号",
    "minCol": 4,
    "id": "control_input_czt1t12vssed",
    "name": "ywh",
    "addins": {
        "txtLayout": "right",
        "unit": "号"
    },
    "visible": false
}
```
<b>文本控件: label </b>
注意事项：纯文本控件，没有输入控件。
````
{
    "type": "label",
    "title": "文本",
    "icon": "title",
    "id": "control_label_ho0hmoaneb8v",
    "name": "control_label_ho0hmoaneb8v"
}
```
<b>密码控件: password</b>
注意事项: 输入框控件的升级版，无特殊配置，指定`type`为`password`即可用。
````
{
    "type": "password",
    "title": "密码",
    "minCol": 4,
    "id": "control_password_sx4cq1rfvtgg",
    "name": "control_password_sx4cq1rfvtgg"
}
```
<b>占位符控件: placeholder</b>
注意事项: 运行时打印时会保留对象位置，但不会在界面上显示。
```
{
    "type": "placeholder",
    "title": "占位符",
    "minCol": 12,
    "id": "control_placeholder_bag438ay3vqi",
    "name": "control_placeholder_bag438ay3vqi"
}
```
<b>二维码控件: qrcode</b>
注意事项: 默认以`value`值作为二维码扫描的内容，在`value`值不存在时，会以`title`作为二维码显示内容。
```
{
    "type": "qrcode",
    "title": "二维码",
    "minCol": 12,
    "id": "control_qrcode_iltsyzbzidp2",
    "name": "control_qrcode_iltsyzbzidp2"，
    "addins": {
        "fixedHeight": 100， //默认值为100px * 100px的正方形
        "simpleLayout": "default" //默认居左排版
    }
}
```
<b>单选框组控件: radiogroup</b>
注意事项: 与多选输入框组类似，注意`list`结构。
```
{
    "type": "radiogroup",
    "title": "单选组框",
    "addins": {
        "list": [
            {
                "label": "Apple",
                "value": "Apple"
            },
            {
                "label": "Pear",
                "value": "Pear"
            },
            {
                "label": "Orange",
                "value": "Orange"
            }
        ]
    },
    "id": "control_radiogroup_z1hnr42gxy6r",
    "name": "control_radiogroup_z1hnr42gxy6r"
}
```
<b>评分控件: rate</b>
注意事项: 无。
```
{
    "type": "rate",
    "title": "评分",
    "count": 5, // 以几颗星显示评分
    "addins": {
        "allowHalf": boolean  //是否允许半分评价
    },
    "id": "control_rate_zp6bz13py480",
    "name": "control_rate_zp6bz13py480"
}
```
<b>富文本控件: richtext2</b>
注意事项: 富文本编辑器的内容存在一个数据库字段中，通常编辑内容较多，在设计这个字段时根据需要将字段大小设置合适。
```
{
    "type": "richtext2",
    "title": "富文本",
    "icon": "github",
    "minCol": 12,
    "id": "control_richtext2_ppmb1ysgvi50",
    "name": "control_richtext2_ppmb1ysgvi50"
}
```
<b>下拉框控件: select</b>
注意事项: 下拉框控件需要注意关键点：`dataSource` `valueName` `labelName`的配合使用，常见错误为正确配置了数据源，但是却无法正确显示。通常是因为没有正确指定`valueName`与`labelName`导致。建议在设计数据源同时指定`valueName`与`labelName`.
```
{
    "type": "select",
    "title": "下拉框",
    "placeholder": "请选择",
    "addins": {
        "searchEnable": false, //输入框是否开启搜索功能 
        "showValue": fasle // 是否在下拉框中显示value
    },
    "valueName": "value",
    "labelName": "label",
    "dataSource": "组织机构"
    "id": "control_select_deyn6l4asp4a",
    "name": "control_select_deyn6l4asp4a"
}
```
<b>进度条控件: slider</b>
注意事项: 无。
```
{
    "type": "slider",
    "title": "进度",
    "min": 1,  // 进度条最小刻度
    "max": 100,  // 进度条最大刻度
    "id": "control_slider_avfpxy3aiggq",
    "name": "control_slider_avfpxy3aiggq"
}
```
<b>步骤条控件: steps</b>
注意事项: 目前步骤为固定内容，如需使用，请扩展该控件。

```
{
    "type": "steps",
    "title": "步骤条",
    "minCol": 12,
    "id": "control_steps_dt55kilax7xf",
    "name": "control_steps_dt55kilax7xf"
}
```
<b>副标题控件: subTitle</b>
注意事项: 无。
```
{
    "type": "subTitle",
    "title": "副标题",
    "minCol": 12,
    "styleType": "arrow", // 其余可选值: slant arrow2 
    "id": "control_subTitle_bmccyvfbzq4n",
    "name": "control_subTitle_bmccyvfbzq4n"
}
```
<b>开关控件： switch</b>
注意事项: 无。
```
{
    "type": "switch",
    "title": "开关",
    "defaultChecked": false,  //默认是否选中
    "checkedChildren": "是",  // 选中时显示的文字
    "unCheckedChildren": "否", // 未选中是显示的文字
    "id": "control_switch_ytk7gvo7az01",
    "name": "control_switch_ytk7gvo7az01"
}
```
<b>多行输入框: textarea</b>
注意事项: 可支持换行操作。
```
{
    "type": "textarea",
    "title": "多行输入框",
    "minCol": 12,
    "minRow": 4,  // 最小行数
    "maxRow": 6,  // 最大行数
    "id": "control_textarea_egua5svkxtoi",
    "name": "control_textarea_egua5svkxtoi"
}
```
<b>时间控件: time</b>
注意事项: 支持[Ant-design 时间控件](https://ant.design/components/time-picker-cn/#API)原生配置
```
{
    "type": "time",
    "title": "时间",
    "id": "control_time_l3fc8t63mzmn",
    "name": "control_time_l3fc8t63mzmn"
    "addins":{
        config: {
            // antd 原生配置
        }
    }
}
```
<b>主标题控件: title</b>
注意事项: 无。
```
{
    "type": "title",
    "title": "主标题",
    "minCol": 12,
    "id": "control_title_c8z0um1g1h1f",
    "name": "control_title_c8z0um1g1h1f"
}
```
<b id="upload2_notice">上传控件: upload2</b>
注意事项: 支持[Ant-design 上传控件](https://ant.design/components/upload-cn/#API)原生配置
PS：在使用中你可能会遇一个提示：<font color='#c41d7f'>提示指定操作的父文件夹不存在</font>。此时打开浏览器`NetWork`会发现`write.do`的请求参数`pid: undefined`或者其它值。这个提示代表没有指定`pid`或者指定`pid`不存在。<br/><font color='#c41d7f'>这里再次强调下：</font>
1、默认的流程视图自带附件文件夹，流程视图中默认不需要配置`pid`，系统默认以业务ID：`business_key`作为了pid。如果流程视图中也遇到了上方这个提示，通常是定义的数据源中没有`business_key`这个键名作为业务ID，你需要将其转换为`business_key`.
2、如果定义的是非业务类型，一般是没有`business_key`的，需要手动配置`pid`，将其作为上传的文件夹。
3、如果明确要把文件上传到指定文件夹，同样设置`pid`实现。
4、表格里的上传控件同样遵循上述三点。
切记以上四点
```
{
    "type": "upload2",
    "title": "上传",
    "addins": {
        "showUploadList": true, // 是否显示上传列表
        "multiple": true, // 是否允许一次性上传多个文件
        "btnTitle": 上传, // 上传按钮的文字
        "pid": "BM0000001", // 上传到目标文件夹的nid，流程视图默认使用业务id作为文件夹的pid，非流程视图需要指定pid
        "config": {
            //antd 原生配置
        }
    }
    "id": "control_upload2_z0m50m165qad",
    "name": "control_upload2_z0m50m165qad"
}
```






##printConfig打印配置

| 属性           | 说明                                                         | 类型                                 | 默认值  |
| -------------- | ------------------------------------------------------------ | ------------------------------------ | ------- |
| manualTxtStyle | 是否启用手动换行文本                                         | <font color='#c41d7f'>boolean</font> | `false` |
| noBorder       | 不打印某条边框，用以组合单元格，可选值为`leftAndRight` `topAndBottom` `leftAndTop` `leftAndBottom` `rightAndTop` `rightAndBottom` `onlyLeft` `onlyRight` `onlyTop` `onlyBottom` `all` `none` | <font color='#c41d7f'>string</font>  | `all`   |
| txtWidth       | 打印时文本的宽度，打印时文本的宽度可能与运行时文本的宽度有不同要求 | <font color='#c41d7f'>number</font>  | `100`   |
|cellSize|	打印为表格时，单元格的大小尺寸，可选取值为`xlg` `lg` `md` `sm` `xs` | <font color='#c41d7f'>string</font> |	`md`
|splitField|	是否以细线分割文本与控件，可选取值为 `0` `1`|	<font color='#c41d7f'>number</font> |	1