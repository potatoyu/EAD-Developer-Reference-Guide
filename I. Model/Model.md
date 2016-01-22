# 模型

## 1 创建模型、实体

### 1.1 创建模型

菜单路径：`开发 > 模型`

![图片名称](https://attachments.tower.im/tower/43450da7dbca4d0bbae7806f226606a9/?filename=Clipboard%20Image.png)

点击 “创建新模型” 动作按钮开始创建新模型，或者选定已经存在的模型点击 “修改” 动作按钮修改模型定义。

![图片名称](https://attachments.tower.im/tower/cdc8e72fc4de49ffa79a2acd9242847a/?filename=Clipboard%20Image.png)

- 模型名称：所要创建模型名称（一般类似于数据库表名）
- 别名：模型的中文名称或英文名称（一般用于页面展示名称一致）
- 继承：继承其他模型及其模型属性
- 类型：模型类型
  - 虚拟（无实际的表与其对应）
  - 存在（有实际的表与其对应）
- 分类：对模型进行分类
- 主题域：一般用于模型分组
- 实体：模型所对应的实际的数据载体，在关系型数据库中就是所对应的表名
- 数据源：实体所在的数据源
- 模式：对应模型操作时，对实体的操作权限
  - safe：安全模式，该模式下，不会对实体有任何操作。
  - alter：更新模式，该模式下，修改模型属性时，会更新实体，并且，如果数据库中实体不存在时，自动配置、创建实体都会进行创建
  - drop：重建模式，该模式下，修改模型属性同更新模式，自动配置、创建实体时，若表存在，则先删除实体，后创建实体。

### 1.2 设置模型属性

菜单路径：`开发 > 模型 > 模型属性`

![图片名称](https://attachments.tower.im/tower/756acff618b34dac8f3ea33088ce8072/?filename=Clipboard%20Image.png)

点击已经创建好的模型，进入“模型属性”设置，点击左上角动作按钮可进行“修改，删除，复制，创建实体，自动配置“等操作。

点击创建实体：在对应的数据源下创建表

> 注意：创建时，参照模型配置模式。

点击自动配置：在对应的数据源下创建数据源，视图，视图属性，资源

> 注意：自动配置资源会默认在开发者中心应用下，需要进行移动


### 1.3 设置虚拟属性

菜单路径：`开发 > 模型 > 模型属性`

![图片名称](https://attachments.tower.im/tower/7140e343262445f78ddd7e945a59bd5a/?filename=Clipboard%20Image.png)

点击"新增"按钮开始添加新模型属性，或者选定已存在的模型属性进行“修改，删除”操作。

![图片名称](https://attachments.tower.im/tower/4bc8b17d0a17423b981d93abf02df8a4?version=auto&filename=Clipboard%20Image.png)

- 名称：模型属性名称，使用字母、数字、下划线组合
- 别名：模型属性的中文名称或英文名称（一般用于页面展示名称一致）
- 类型：模型属性类型
  0. 直接量
  0. 外键关系
  0. JSON对象
  0. JSON数据
  0. 单例模型
  0. 模型集合
  0. 链接

 > 注意：其中,1~4 所对应的值都会从数据库实体中获取到，5~6 用于配置一对一、一对多（父子模型），7 用于配置链接地址

- 数据类型：用来表示所创建模型属性的数据类型，详细信息参照 `开发 > 类型`

  > 注意：除普通类型完，模型本身也可以作为数据类型，当模型属性类型为**单例模型或模型集合**时，必须选择数据类型为模型。

- 枚举列表：当该属性的值需要从列表中进行选择时，需要设置枚举列表，设置方法如下：

  > 第一种：*工艺,设备,仪表,电气*。第二种：*technology:工艺,equ:设备,instrument:仪表,electric:电气*
  > 注意：其中的分隔字符都为英文字符（半角字符）。

- 虚拟属性
  - 是，在该模型对应的数据库实体中不创建，但在视图上会进行展示。（联合查询后的字段）
  - 否，在该模型对应的数据库实体中会创建。
  - 默认

  > 注意：一般*留空*，或者当要进行数据联合展示时，选择*是*即可
 
- 表单：浏览器中操作时，展现的填写表单
- 必须：设置后，该属性在填报时必须填写
- 唯一：设置后，该属性在表单提交是进行唯一性校验
- 默认值：默认值填写后，表单中会自动出现该值
- 系统：是否系统自动填写字段，填写的值为设置的默认值
  - 否，非系统自动填写
  - 只创建，创建时系统自动填写，如创建时间。
  - 只更新，更新是系统自动填写
  - 可写，创建和更新时系统填写
- 数据字典：该属性的值是从其他表中选择得到的，此处选择一个字典视图。
- 键类型：分为物理主键和联合主键
  - 物理主键，一个模型有且仅有一个物理主键
  - 联合主键，一般用户联合唯一性校验
- 外键：当前属性类型为单例模型或模型集合时，需要指定当前模型的那一个属性与数据类型中选择的模型所关联。

### 1.4 绑定数据源

菜单路径：`开发 > 数据源`

![图片名称](https://attachments.tower.im/tower/14f134749f87420bb4823a9510f78334?version=auto&filename=Clipboard%20Image.png)

点击“数据源”按钮，开始新增一个“数据源”，或者选定已存在“数据源”进行“修改，删除，启动，关闭”操作。

![图片名称](https://attachments.tower.im/tower/bb8f2bb1ee324bc0985c05ff4648398d?version=auto&filename=Clipboard%20Image.png)

- 名称：数据源名称，使用英文字符
- 类型：选择需要加入的数据库类型
- 驱动：选择数据库的连接驱动
  - mysql：com.mysql.jdbc.Driver
  - oracle:oralce.jdbc.driver.OracleDriver
- IP：数据库IP地址
- 端口：数据库端口
  - mysql：3306
  - oracle：1521
- 库名：
  - 实际的数据库名称
- 链接：
  - Mysql：jdbc:mysql://{ip}:3306/{库名}?useUnicode=true&characterEncoding=UTF-8&zeroDateTimeBehavior=convertToNull
  - Oracle：jdbc:oracle:thin:@{ip}:1521:{库名}
- 用户名：数据库用户名
- 密码：数据库密码
- 最大连接：最大连接数
- 最小连接：最小连接数
- 启动模式：
  - 自动：应用启动时，随应用启动
  - 手动：应用启动时不启动，应用启动后手动启动

### 1.5 创建数据实体

菜单路径：`开发 > 模型`

![图片名称](https://attachments.tower.im/tower/d11833583f014c73a26a6b1c454f3b07?version=auto&filename=Clipboard%20Image.png)

选定创建好的模型，可对该模型进行“创建实体”操作（必须为模型添加“实体，数据源”）

# 数据集

## 2. 创建数据集

### 2.1 快速创建数据集

菜单路径：`开发 > 数据集`

![图片名称](https://attachments.tower.im/tower/c4a4bf72646c44ae8e8d722f103ec6d4?version=auto&filename=Clipboard%20Image.png)

点击“创建新数据集”动作按钮，开始创建新数据集，或者选定已经存在的数据集，可对数据集进行“修改，删除，复制”操作。

![图片名称](https://attachments.tower.im/tower/fbb2b5c6f3d844d89128b4e1c8dfb167?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/08c62658172a4e72a0b78a47e7cde742?version=auto&filename=Clipboard%20Image.png)

- 名称：数据集名称
- 模型：数据集所对应的模型
- 查询定义：暂时无需设定
- 最大条数：暂时无需设定
- 原生查询：原生SQL
- 属性映射：暂时无需设定
- 查询类型：
  - 默认，系统默认
  - 自定义，需要自己编程
- 集合类型：暂时无需设定
- 数据源：必须选择数据源
- 集合描述：
- 集合分类：

# 视图

## 3. 创建视图、动作、过滤器

### 3.1 创建视图

菜单路径：`开发 > 视图`

![图片名称](https://attachments.tower.im/tower/c5846f1fb5d441fcbb6e7317c4c6563b?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/3024e25a220a4c1788446713da021f59?version=auto&filename=Clipboard%20Image.png)

点击“新建视图”动作按钮，开始新建视图，或者选定已经存在的视图，可对视图进行“修改，删除，复制”操作。

![图片名称](https://attachments.tower.im/tower/ad54c67b32e84f338802e1528eddfcb5?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/04c759e90b684119898cdbbb46882e66?version=auto&filename=Clipboard%20Image.png)

- 名称：视图名称
- 显示：视图显示的样式
  - 表格
  - 数据表格
  - 树形
  - 日历
  - 排程
  - 表单
- 模型：选择视图所使用的模型
- 查询：选择视图所使用的数据集
- 分类：视图分类
- 参数：视图参数，格式为：{"pagination":"size","nodeName":"","size":"15","handle":"true"}

  > 注意：当视图为树形视图时，需要指定nodeName，及模型属性中父节点的名称；
  > 当视图为日历或排程视图时，需要start_time和end_time。

- 查询参数：可以设置查询参数，用于替换查询中的变量，格式为：{"param":[{"name":"{查询变量}","value":"{值}"}]}，如：{"param":[{"name":"uid","value":"${uid}"}]}
- 描述：
- 模版：可忽略
- 缓存：可忽略
- 前端参数：可忽略
- 事件：可忽略
- 图标：根据Bootstrap组件字体图标添加
- 设置：可忽略
- 异步：可忽略
- 操作类型：当前视图可进行的操作的类型，单项操作或多项操作
- 布局：可忽略
- 扩展：可忽略

### 3.2 设置视图属性

菜单路径：`开发 > 视图 > 属性`

![图片名称](https://attachments.tower.im/tower/3024e25a220a4c1788446713da021f59?version=auto&filename=Clipboard%20Image.png)

选定已经存在的视图属性或者新建一个视图，进入视图选择属性。

![图片名称](https://attachments.tower.im/tower/921bb3be3025427eae5f35b71047d5f5?version=auto&filename=Clipboard%20Image.png)

点击"新增"动作按钮，开始新建视图属性，或者选定已经存在的视图属性，对该视图属性进行"修改，删除"操作。

![图片名称](https://attachments.tower.im/tower/7f0ab5580d5642648819fa10b7187b11?version=auto&filename=Clipboard%20Image.png)

- 名称：属性名称，会显示到界面表头上
- 模型属性：属性所对应的模型属性
- 表单：操作时，显示的表单类型
- 字典模式：当该字段为数据字典时，获取数据的方式
  - all，全部，获取全部的字典数据
  - bydata，根据查询到的列表数据返回字典数据
- 显示模式：
  - title，若该属性可以通过超链接点进去，查看详细内容及子视图，则需要设置为title
- 权限：
  - 可写，该属性可以新增和编辑
  - 只创建，该属性只可以新增
  - 只更新，该属性只可以更新
  - 只读，该属性的值会查询并发送到浏览器
  - 禁止，该属性的值不会发送到浏览器
- 绑定视图：当该属性所对应的模型属性为单例模型或模型集合时，需要绑定相应的子视图
- 隐藏：浏览器界面隐藏设置
  - 列表，列表上隐藏
  - 全部，列表及详细视图中都隐藏
- 默认值：类似于模型属性默认值，该默认值与模型属性中的默认值按就近原则处理
- 序号：界面上数据显示的顺序
- 分组：设置分组项后，会在详细内容中进行分组
- 系统：类似于模型属性的系统，该系统与模型属性中的系统按就近原则处理
- Format：暂不设置
- Display：暂不设置
- Column：暂不设置

### 3.3 创建视图动作

菜单路径：`开发 > 视图 > 动作`

![图片名称](https://attachments.tower.im/tower/f356442931b54279ae328e212d3e2b56?version=auto&filename=Clipboard%20Image.png)

点击"新增"动作按钮，开始新建视图动作，或者选定已经存在的视图动作，对该视图动作进行"修改，删除"操作。

![图片名称](https://attachments.tower.im/tower/60a18c115b64486eb1760d7029676080?version=auto&filename=Clipboard%20Image.png)

- 名称：动作名称，即显示到界面上按钮的名称
- 编码：动作编码，使用英文字符。新增、修改、删除时无需设置
- 类型：暂不设置
- 驱动：通用新增、修改、删除无需设置，其他需要选择相应的驱动
- 动作参数：通用新增、修改、删除无需设置，其他按需要设置
- 属性列表：当前动作可操作的视图属性列表中的子集
- 前端事件：通用新增、修改、删除无需设置，其他需要按需设置
- 前端参数：暂不设置
- 图标：界面按钮上显示的图标
- 选择模式：数据选择不同，可进行的操作不同
  - 无选，无选时，出现该按钮
  - 单选，单选时，出现该按钮
  - 有选，有选时，出现该按钮
  - 多选，多选时，出现该按钮
- 主要：设置为主要，颜色会在界面加深
- 分组：设置分组后，按钮会分组显示
- 操作视图：默认该按钮操作当前视图，可设置该按钮操作不同视图
- HTTP方法：HTTP方法
- 显示模式：暂不设置
- 表单控件：暂不设置
- 允许手机：暂不设置

### 3.4 创建视图过滤器

菜单路径：`开发 > 视图 > 过滤器`

![图片名称](https://attachments.tower.im/tower/4d29772001274c61a45efc26a6451675?version=auto&filename=Clipboard%20Image.png)

点击"新增"动作按钮，开始新建视图过滤器，或者选定已经存在的视图过滤器，对该视图过滤器进行"修改，删除"操作。

![图片名称](https://attachments.tower.im/tower/6bfaa79e70a842bface74bbc8941ebec?version=auto&filename=Clipboard%20Image.png)

- 视图属性：选择要过滤的属性列
- 名称：过滤器名称
- 类型：
  - 条件，过滤筛选
  - 排序，数据排序
- 条件：
  - 等于
  - 不等于
  - 大于
  - 小于
  - 大于等于
  - 小于等于
  - 相似
  - 区间
  - 树
  - 升序
  - 降序
- 参数：
- 默认值
- 必须
- 辅助：
- 表单控件：
- 表单参数：
- 是否区间：
- 排序：
- 隐藏：

# 应用

## 4. 添加应用资源、资源授权

菜单路径：` 应用 > 应用`

![图片名称](https://attachments.tower.im/tower/d898c676ef2e4f94824b16b01bfe6465?version=auto&filename=Clipboard%20Image.png)

点击"创建新应用"动作按钮，开始新建应用资源，或者选定已经存在的应用资源，对该应用资源进行"修改，删除"操作。

![图片名称](https://attachments.tower.im/tower/be6172d5ec6148439c187e2724a9a1dc?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/cf2158f05cfe4d819c280e1ca2670e68?version=auto&filename=Clipboard%20Image.png)

- 应用ID：
- 应用描述：
- 路径：
- 应用URL:
- 会话类型：
- 语言：
- 应用参数：
- 应用模版：
- 应用主题：
- 应用样式：
- LOGO：

菜单路径：` 应用 > 应用 > 资源`

![图片名称](https://attachments.tower.im/tower/00e2c0da1f3945a886bc70b81ca09a67?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/dca19c982526492db1870c396e1dc790?version=auto&filename=Clipboard%20Image.png)


进入应用选择资源，点击“新增”动作按钮添加资源，或者选择已经存在的资源，对该资源进行“修改，删除”操作。

![图片名称](https://attachments.tower.im/tower/38ad3218b7df44e1b36c74e57938ea6b?version=auto&filename=Clipboard%20Image.png)

- 资源编码：
- 父资源：
- 资源级别：
- 资源类型：
- 资源对象：

菜单路径：` 应用 > 应用 > 角色`

![图片名称](https://attachments.tower.im/tower/03e3fcddafd2470b952d51933e3d08d8?version=auto&filename=Clipboard%20Image.png)

进入应用选择角色，点击“新增”动作按钮添加角色，或者选择已经存在的角色，对该角色进行“修改，删除，授权 复制”操作。

![图片名称](https://attachments.tower.im/tower/326b11a0fab547bea610f4f2d3b54a47?version=auto&filename=Clipboard%20Image.png)

- 角色编码：
- 角色描述：

# 高级配置

## 5. 高级模型设置

### 5.1 设置系统变量默认值

菜单路径：` 配置 > 系统变量 `

![图片名称](https://attachments.tower.im/tower/8597bc19757e4e20905badca4e60561e?version=auto&filename=Clipboard%20Image.png)

点击"新增"动作按钮，开始新增变量，或者选定已经存在的变量，对该变量进行"修改"操作。

- 变量类型：
- 变量类别：
- 变量分类：

### 5.2 设置属性数据字典

菜单路径：` 开发 > 视图 `

![图片名称](https://attachments.tower.im/tower/5a7235f0c84c416abeed60a2691aae21?version=auto&filename=Clipboard%20Image.png)

选中要修改的视图，复制一个新的视图

![图片名称](https://attachments.tower.im/tower/a59cd815ff424406bd8ce5ddefc6aae3?version=auto&filename=Clipboard%20Image.png)

修改视图名称，类型，显示模式，删除参数

![图片名称](https://attachments.tower.im/tower/b07bce950c0f4f5db76f7895bad91a9e?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/ece57713c4d149c9a65f2afd03b9fb41?version=auto&filename=Clipboard%20Image.png)

进入该视图的视图属性，将不需要的视图属性删除，保留主键，主要信息，数据状态（保留可用视图属性）

![图片名称](https://attachments.tower.im/tower/9c5b3cc240074851b1973a984f151d94?version=auto&filename=Clipboard%20Image.png)

删除动作以及过滤器中的属性

![图片名称](https://attachments.tower.im/tower/c9d2f7bbe1a74379bf2d2d1b3ad66b05?version=auto&filename=Clipboard%20Image.png)





### 5.3 设置属性子视图



### 5.4 模型继承



## 6. 基于模型快速创建视图资源

## 7. 自定义驱动

### 7.1 自定义数据集查询驱动

### 7.2 自定义视图动作驱动

### 7.3 自定义视图驱动

## 8.记录

- 添加可选状态的数据

![图片名称](https://attachments.tower.im/tower/ec11c33664bc463cb230c3d5caca38b9?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/956f76419035465588fbb3d0b75208a6?version=auto&filename=Clipboard%20Image.png)
![图片名称](https://attachments.tower.im/tower/e10e528162414bb09b1ad3d420a8ee29?version=auto&filename=Clipboard%20Image.png)

![图片名称](https://attachments.tower.im/tower/56546daf215944cbb1459c1afa55c08d?version=auto&filename=Clipboard%20Image.png)
![图片名称](https://attachments.tower.im/tower/5ac3cfbd6c1241d0bf7d58f1f9a52a92?version=auto&filename=Clipboard%20Image.png)

# 工作流

## 9. 创建工作流

### 9.1 创建工作流模型

菜单路径：` 开发 > 工作流 > 模型 `

- 模型名称：流程名
- 模型别名：流程别名
- 模型流程图：暂无设置
- 说明：流程的说明
- 序号

### 9.2 创建工作流步骤

菜单路径：` 开发 > 工作流 > 模型 ： 步骤 `

- 步骤名称：工作流步骤名称
- 步骤编码：步骤编码，在同一个工作流中，编码不能重复
- 步骤类型：
  - 起始步骤：工作流开始步骤，只有一条开始步骤
  - 中间步骤：工作流中间步骤
  - 结束步骤：工作流结束步骤，只有一条结束步骤
- 前置步骤：当前步骤的前一步
- 后置步骤：当期步骤的后一步
- 参与用户：当前步骤的审批用户
- 参与角色：当前步骤的审批者的角色
- 参与组织：当前步骤的审批者的所属组织

> 注意：参与用户、参与角色、参与组织 配合使用规则：
> 1：参与用户不为空时，忽略参与角色与参与组织
> 2：参与角色和参与组织配合使用，一般需要两个都填写，如：生产运行部（参与组织） + 部室副主任（参与角色）

- 超时时间，暂时未启用
- 超时事件，暂时未启用
- 状态说明
- 数据条件，当前步骤的下一步的执行条件，举例如下：当前数据的停机专业为不同的停机专业，按照步骤编码，查找不同的下一步步骤：

```
[
    {
        "condition":"\"${stop_profession}\"  == \"设备\"",
        "step_code":"10"
    },
    {
        "condition":"\"${stop_profession}\"  == \"仪表\"",
        "step_code":"20"
    },
    {
        "condition":"\"${stop_profession}\"  == \"电气\"",
        "step_code":"30"
    },
    {
        "condition":"\"${stop_profession}\"  == \"工艺\"",
        "step_code":"40"
    }
]
```

- 消息模板：暂时未启用
- 回退步骤：当前步骤不通过退回时，要退回的步骤，一般情况默认为空，按照系统默认进行退回即可。
- 事件通知：暂时未启用
- 表单参数：如果在流程过程中，有审批者需要填写的内容，需要在表单参数中设置需要填报项，设置方法如下：

```
["stop_examine","money"]
```

- 操作者条件：若当前步骤的审批信息来自于当前填写的表单，则需要设置操作者条件，设置方法如下：

```
{
    "act_user":[""],
    "act_org":["second_operate_org"],
    "act_role":["second_operate_org"]    
}
```
> 注意：只需按需要设置其中的一项或者多项，查找规则类似于参与用户、参与组织、参与角色

- 允许跳过：是否允许跳过当前步骤
- 是否完成：是否允许办结当前的流程
- 是否允许退回起点：审批者可以直接退回当前流程到填报者
- 是否退回起点：设置该项后，如果当前步骤不通过，则直接退回填报者
- 步骤序号：步骤的排序
- 回调驱动：暂不设置

## 10、绑定工作流

创建带有流程的模型，需要继承与流程模型：$workflow
创建带有流程的模型视图时，一般需要配置三个视图：填报视图、审批视图、审批查询视图，以便于填报、审批、审批查询。

### 10.1 创建上报视图及视图动作

上报视图配置时，除新增、修改、删除，还需要配置**上报**的视图动作，配置如下：

名称：上报
编码：report
驱动：flowReport
前端事件：one
图标：glyphicon-share-alt
选择模式：单选
主要：勾选
分组：1
工作流模型：选择当前表单要进行的流程
HTTP方法：POST
![图片名称](https://attachments.tower.im/tower/cc8071c8cf5f4f80888008d1bc3dcc19?filename=%E4%B8%8A%E6%8A%A5-1.png)
![图片名称](https://attachments.tower.im/tower/9c8590fe87b74ac68e14e947a2eae009?filename=%E4%B8%8A%E6%8A%A5-2.png)


### 10.2 创建审批视图及视图动作

审批视图配置时，需要配置**审批**视图动作，配置如下：

名称：审批
编码：check
驱动：flowCheck
前端事件：check
图标：glyphicon-check
选择模式：单选
主要：勾选
分组：1
工作流模型：选择当前审批的工作流模型
HTTP方法：POST

![图片名称](https://attachments.tower.im/tower/1f768fc882464673abd8cb3971f512b9?filename=%E5%AE%A1%E6%89%B9-1.png)
![图片名称](https://attachments.tower.im/tower/d26c4a91241c445587922319329ffb18?filename=check-2.png)

### 10.3 创建审批查询视图及动作


# 常用配置及案例

## 模型

### 普通模型

### 日历模型

### 工作流模型

## 数据集

### 普通数据集

### 综合展示数据集

### 字典数据集

### 工作流上报者数据列表数据集

### 工作流审批列表数据集

### 工作流审批数据查询数据集

## 视图

### 普通视图

### 日历视图

### 网盘视图

### 视图属性

### 视图过滤器

### 视图动作

#### 新增 

属性名称 | 属性值 | 说明
------- | ----- | ---
名称 | 新增xxx | --
编码 | --- | --
类型 | --- | --
驱动 | --- | 若有特殊需求，先在驱动表中注册，然后再选择
动作参数 | -- | --
属性列表 | -- | --
前端事件 | -- | --
前端参数 | -- | --
图标 | glyphicon-plus | --
选择模式 | 无选 | --
主要 | 勾选 | --
分组 | 1 | --
描述 | 新增xxx | --
操作视图 | -- | --
工作流模型 | -- | --
HTTP方法 | POST | --
显示模式 | -- | --
表单控件 | -- | --
允许手机 | -- | --
规则 | -- | --
序号 | 10 | --

#### 修改

属性名称 | 属性值 | 说明
------- | ----- | ---
名称 | 修改 | --
编码 | --- | --
类型 | --- | --
驱动 | --- | 若有特殊需求，先在驱动表中注册，然后再选择
动作参数 | -- | --
属性列表 | -- | --
前端事件 | -- | --
前端参数 | -- | --
图标 | glyphicon-pencil | --
选择模式 | 单选 | --
主要 | 不勾选 | --
分组 | 1 | --
描述 | 修改xxx | --
操作视图 | -- | --
工作流模型 | -- | --
HTTP方法 | PUT | --
显示模式 | -- | --
表单控件 | -- | --
允许手机 | -- | --
规则 | -- | --
序号 | 20 | --

#### 协同修改

属性名称 | 属性值 | 说明
------- | ----- | ---
名称 | 自我命名 | 自我进行命名
编码 | 自我编码 | 必须对协同修改的按钮进行编码
类型 | --- | --
驱动 | --- | 若有特殊需求，先在驱动表中注册，然后再选择
动作参数 | -- | --
属性列表 | 属性列表子集 | 填写需要修改的属性列
前端事件 | -- | --
前端参数 | -- | --
图标 | glyphicon-pencil | --
选择模式 | 单选 | --
主要 | 不勾选 | --
分组 | -- | --
描述 | 修改xxx | --
操作视图 | -- | --
工作流模型 | -- | --
HTTP方法 | PUT | --
显示模式 | -- | --
表单控件 | -- | --
允许手机 | -- | --
规则 | -- | --
序号 | 自我进行编号 | --

#### 删除

属性名称 | 属性值 | 说明
------- | ----- | ---
名称 | 删除 | --
编码 | --- | --
类型 | --- | --
驱动 | --- | 若有特殊需求，先在驱动表中注册，然后再选择
动作参数 | -- | --
属性列表 | -- | --
前端事件 | -- | --
前端参数 | -- | --
图标 | glyphicon-trash | --
选择模式 | 有选 | --
主要 | -- | --
分组 | -- | --
描述 | 删除xxx | --
操作视图 | -- | --
工作流模型 | -- | --
HTTP方法 | DELETE | --
显示模式 | -- | --
表单控件 | -- | --
允许手机 | -- | --
规则 | -- | --
序号 | 30 | --

#### 点击后根据配置更新数据

属性名称 | 属性值 | 说明
------- | ----- | ---
名称 | 自我命名 | 比如“维修”
编码 | 自我命名 | 必须进行编码，如：repair
类型 | --- | --
驱动 | updateBySetting | 必须选择该驱动
动作参数 | {"update":{"if":{"status":["正常"]},"then":{"status":"维修"}}} | 根据前置条件去更新，前置条件可为空
属性列表 | -- | --
前端事件 | batch | --
前端参数 | -- | --
图标 | 自我选择按钮图标 | --
选择模式 | 有选 | --
主要 | 自我选择是否勾选 | --
分组 | 自我进行分组 | --
描述 | 自我填写描述 | --
操作视图 | -- | --
工作流模型 | -- | --
HTTP方法 | POST | --
显示模式 | -- | --
表单控件 | -- | --
允许手机 | -- | --
规则 | -- | --
序号 | 自我编号 | --

- 上报
- 审批
- 审批记录

## 案例