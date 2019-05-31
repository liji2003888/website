+++
title = "字段定义"
description = "介绍如何进行组织层的自定义字段设置"
weight = 9
+++

# 字段定义

字段定义页面中会显示出字段方案列表，组织管理员可以对本页中的所有字段方案进行编辑，然后到 `页面` 菜单中对字段显示进行设置从而实现组织下问题类型页中字段的自定义。目前的字段定义中只存在 `敏捷问题字段方案` 。

{{< note >}}
组织层只能编辑组织层创建的字段，项目层创建的字段不会在组织层显示。
{{</ note >}}

- **菜单层次**：组织层
- **菜单路径**：组织设置 > 字段定义
- **默认角色**：组织管理员

## 什么是字段定义

字段定义是指在组织层对敏捷问题类型中的字段的一系列操作，包括增加，删除，修改，编辑等。实现不同组织对敏捷问题类型中字段的个性化需求和同一组织下项目层页面的整洁度和条理性。

{{< note >}}
组织初始的敏捷问题类型方案的中预置字段不允许编辑。
{{</ note >}}

<h2 id="1">字段定义列表</h2>

![](/docs/user-guide/system-configuration/tenant/image/custom-field-1.png)

1. 筛选器：可以按照名称对字段方案进行筛选。
2. 方案名称：字段定义方案的名称。
3. 方案类型：字段定义方案的类型。
4. 字段方案列表字段设置：控制字段方案列表中列是否显示。
5. 编辑按钮：进入编辑方案页面。

<h2 id="2">编辑方案</h2>

编辑方案页面会显示出该字段方案下的所有字段及其属性，您可以在本页面对方案下字段进行添加、删除和编辑。

{{< note >}}
系统预设字段不能进行更改。
{{</ note >}}

{{< note >}}
组织层只展示组织层创建的字段，无法显示项目层创建的字段。
{{</ note >}}

![](/docs/user-guide/system-configuration/tenant/image/custom-field-2.png)

1. 点击此处创建一个新的字段。
2. 字段：字段名称是唯一的，不可以重复。
3. 显示范围：字段可显示范围包括 `全局` 、 `特性` 、 `史诗` 、 `故事` 、 `缺陷` 、 `任务`、 `子任务` 七种范围。
4. 字段类型：在字段中包括 `单选框` 、 `复选框` 、 `时间选择器` 、 `日期时间选择器` 、 `数字输入框` 、 `文本框（单行）` 、 `文本框（多行）` 、 `选择器（单选）` 、 `选择器（多选）` 九种类型。
5. 必选项：设置该字段在创建时是否为必填。
6. 删除按钮：删除该字段。
7. 编辑按钮：对该字段进行编辑。

<h2 id="3">添加字段</h2>

字段是项目中问题详情的属性，能够让团队人员更清晰了解问题详情，在这个页面，你将了解如何在字段方案内添加一个新的字段。

![](/docs/user-guide/system-configuration/tenant/image/custom-field-3.png)

点击添加字段按钮（在编辑方案页面上部）进行字段添加。

![](/docs/user-guide/system-configuration/tenant/image/custom-field-4.png)

1. 编码：字段编码是唯一的，不可以重复。

{{< note >}}
只允许数字、字母以及下划线，上限10个字。
{{</ note >}}

2. 名称：字段名称是唯一的，不可以重复。

{{< note >}}
用户自行填写，上限15字。
{{</ note >}}

3. 字段类型：选择字段类型，可选 `单选框` 、 `复选框` 、 `时间选择器` 、 `日期时间选择器` 、 `数字输入框` 、 `文本框（单行）` 、 `文本框（多行）` 、 `选择器（单选）` 、 `选择器（多选）` 。
4. 显示范围：选择字段显示范围，可选 `全局` 、 `特性` 、 `史诗` 、 `故事` 、 `缺陷` 、 `任务` 、 `子任务` 。

<h2 id="4">编辑字段</h2>

编辑字段是指对一个添加的字段进行具体操作，包括查看、设置默认值、添加值等。

![](/docs/user-guide/system-configuration/tenant/image/custom-field-5.png)

点击 `编辑` 按钮 -> ![修改](/docs/user-guide/system-configuration/tenant/image/update.png)进行字段编辑。

![](/docs/user-guide/system-configuration/tenant/image/custom-field-6.png)

1. 添加：添加字段的值。
2. 默认值：设置字段默认的值，可选项为下方文本框中用户自行添加的值。
3. 添加好的值显示在文本框中，可以通过拖拽改变值的显示顺序。
4. 编辑按钮：编辑已创建值的值。
5. 禁用按钮：禁用值，被禁用的值不会在字段选项列表中显示。
6. 删除按钮：删除值。

{{< note >}}
新添加的字段默认为不显示，需要在 `页面` 中进行勾选。
{{</ note >}}