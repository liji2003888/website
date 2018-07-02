# Changelog

本文档记录了Choerodon 0.7.0中**微服务开发框架**、**持续交付**和**敏捷管理**等功能的增强、变更等。

## Choerodon 微服务开发框架
### [0.7.0] - 2018-06-29
### 新增

#### 0.7.0显著新增特性

- 新增实例管理，可以查看微服务框架中的所有正在运行的实例。
- 新增配置管理，可以管理微服务中服务的配置，并对配置进行修改，创建，设为默认等。
- 个人信息页字段丰富，用户修改头像添加裁剪功能。

#### 控件0.3.2

- Select组件新增 loading 属性，获取异步数据时，可置为loading状态。
- 增加 `isModifiedFields`, `isModifiedField` 方法。

#### boot0.6.2

- 增加文件服务配置属性`fileServer`。
- 增加注入环境变量配置属性`enterPoints`函数。

#### 框架的依赖0.5.3

- `choerodon-starter-core`添加了`InitRoleCode`常量类。
- `choerodon-tool-liquibase`数据库迁移添加了忽略指定表或者列的功能。

### 修改

#### 0.7.0显著修改特性

- 个人信息修改了界面样式
- 页面菜单样式修改，由之前的固定在左侧变为可以收缩展开。

#### 控件0.3.2

- `Table`: 排序图标样式调整。
- `Select` `Input` `Radio` `DatePicker`: 样式调整。

#### boot0.6.2

- 完善多语言文案。
- 菜单初始化逻辑修改。

#### 框架的依赖0.5.3

- `choerodon-tool-config`修改为每次初始化只更新`is_default`的配置，而不是每次产生新配置。
- `choerodon-starter-bus`修改为服务拉取配置时，当`bus`消息的版本字段为空时拉取实例正在应用的配置，而不是拉取默认配置。
完善 `agent websocket` 连接参数条件判断。

### 修复

#### 0.7.0显著修复特性

- 修复了表格中样式对齐和行间距的问题。
- 修复了403、404页面自适应的问题。
- 修复了组织管理中由于多语言引起的组织管理启停用提示错误、编码字符限制无提示、修改功能不可用等问题。
- 修复了菜单配置中目录编码重复无提示、空目录保存后消失、提示样式不固定等问题。
- 修复了角色管理中创建角色没有跳转到列表页、权限为空报错提示触发条件错误等问题。
- 修复了角色分配中过滤角色跳转到白页、将成员角色全部删除后未清除成员数据、列表中角色与成员未对齐等问题。
- 修复了Root用户设置中滤时查询的不是root用户而是所有用户、点击刷新后倒序消失的问题。
- 修复了微服务管理中ChoerodonExtraData路由刷不进去、yml文件显示null的问题。
- 修复了用户管理中由于多语言引起的时区没有默认值、登录名和密码输入框报错提示为英文的问题。
- 修复了LDAP无数据时同步用户一直处于loading状态、测试连接数组越界等问题。
- 修复了项目信息项目名称为空无判断的问题。
- 修复了个人中心修改密码的新密码与原密码相同时后端报错的问题。
- 修复了后端框架中验证码区分大小写、更新网关配置出现的异常、快码查询接口500错误等问题。

#### 框架的依赖0.5.3

- `choerodon-starter-bus`修复没有`@EnableEurekaClient`注解时会出现的缺少`eurekaRegistrationbean`的异常。
- `choerodon-starter-oauth-core`修复密码策略中正则策略异常。

### 删除

#### 0.7.0显著删除特性

- 删除了角色分配旧接口权限。
- 删除了文件管理在组织、项目层角色的权限。

### 框架的依赖0.5.3

- `choerodon-starter-swagger`扫描到的`controller`去除了`BasicErrorController`。
- `choerodon-starter-core`删除了`@Permission`注解的`roles`字段默认值。

## 持续交付
### [0.7.0] - 2018-06-29
### 新增

- `应用导出`，以便在其他平台使用该平台研发的应用。
- `应用导入`，以便导入其他平台研发的应用并部署使用。
- `实例`、`网络`、`域名发现`，以便平台进行自我管理和升级。
- `网络管理`实例不可用验证。
- `网络端口`合法性验证。
- `域名管理`网络不可用验证。
- `域名管理`Path地址重复性验证。
- 每个权限上增加默认角色。
- 停用环境时校验该环境下不能存在网络及域名设置。
- `应用发布`及`应用部署`增加取消按钮。
- 配置信息校验yaml格式报错并展示具体报错信息。
- 支持中英文模式。
- 支持gitlab升级为新版本v11.0.1。


### 修改

#### 0.7.0显著修改特性

- 后台报错支持中英文翻译。
- 修改两个API命名使其符合命名规范及权限检查规范。
- 优化用户获取预定义应用模板获取方式，无需再手工创建。
- 表格列宽自适应。
- 统一页面中表格表头的命名标准。
- 优化网络管理代码质量。
- `网络名称`不可修改。
- 去除应用的`仓库地址`相同部分的冗余显示。
- 应用图标上传使用相对路径。
- 优化实例单应用界面选择应用的展示方式，默认显示项目`应用`及`应用市场`两个分类，可扩展显示更多。


### 修复

#### 0.7.0显著修复特性

- `应用部署`时`Values`替换错乱。
- `持续集成流水线`时长不准确。
- `应用市场`中应用详情README在部分情况下无法获取。
- 优化`持续集成`分步请求API导致的界面延迟问题。
- 个别表格分页的缺陷。
- 根据应用筛选对应`应用版本`时，值集过多的缺陷。
- 完善应用版本页面的提示语。
- `持续集成流水线`缺少`tag`类型最新流水线`Latest`标识的缺陷。
- 了解详情链接点击后在本页打开的缺陷。
- 配置信息页面在页面缩放时yaml行高计算不准确的缺陷。

## 敏捷管理
### [0.6.0] - 2018-06-29
### 新增

- `问题链接`功能：用户可以在问题详情选择链接类型链接对应的问题，创建项目会默认3个类型：`阻塞`、`复制`、`关联`，支持在设置功能自定义链接类型。
- `版本归档`功能：归档一个版本的状态改为归档。
- `版本合并`功能：撤销归档，版本状态回到上一个状态。
- `冲刺报告`功能：记录进行中以及结束的冲刺的问题统计，包括冲刺期间`已完成`的问题、`未完成`的问题、从冲刺中`删除`的问题，用户选择冲刺后，可以查看当前选择冲刺的报告记录以及当前选择冲刺的简易燃尽图。
- `冲刺燃尽图`报告功能：记录进行中以及结束的冲刺中问题的操作事件并生成报告以及图表信息，选择冲刺后可以通过剩余预估时间、故事点、问题计数对问题（包含子任务）进行统计。
- `自定义项目编码`功能：用户可以在设置中的项目设置对项目的编码进行修改，修改后体现在问题编号上。
- `活动日志`功能：问题的更新操作都将被记录在活动日志中，可以在问题详情中查看，冲刺统计信息都从活动日志中生成。
- `自定义筛选器`功能：用户可以在设置中的快速搜索创建自定义筛选器，筛选器能够以`字段`、`类型`、`数值`进行配置，并在问题管理和待办事项中应用自定义筛选器。
- `面板泳道设置`功能：可以在面板设置中对泳道进行设置，泳道可以根据`故事`、`经办人`、无在进行界面上进行展示。

### 改变

- `冲刺`与`问题`的一对一关系改为多对多。
- `创建问题``子任务`状态与`父问题`状态相同。
- 支持删除计划中的`冲刺`。
- 新增菜单：`报告`、`设置`，设置包含子菜单：`项目设置`、`快速搜索`、`问题链接`。
- 所有页面接口增加权限。
- 待办事项的`史诗`、`版本`可以通过问题是否完成展示进度条。
- 创建冲刺时定位到新创建的冲刺。
- 可以在问题详情中对问题状态进行修改。
- 时间选择器精确到秒。
- 待办事项批量选中问题支持ctrl键选中。

### 修复

- 部分用户信息不包含头像信息。
- 选择经办人只能选择20条数据。
- `问题详情`锚点监听不准确。
- `问题管理`缺陷类型筛选失效。