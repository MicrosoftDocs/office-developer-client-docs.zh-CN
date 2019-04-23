---
title: Open 方法（ADO 记录）
TOCTitle: Open method (ADO Record)
ms:assetid: ba71c5c7-326e-d3b6-0e74-e8343ee6896f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249896(v=office.15)
ms:contentKeyID: 48547371
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: db8953cafc5ad266c81c51e59cbf92787d07cdfb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288376"
---
# <a name="open-method-ado-record"></a>Open 方法（ADO 记录）

**适用于**：Access 2013、Office 2013

用于打开现有的 [Record](record-object-ado.md) 对象，或创建由 **Record** 表示的新项（如文件或目录）。

## <a name="syntax"></a>语法

开放*源代码*、 *ActiveConnection*、 *Mode*、 *CreateOptions*、 *Options*、 *UserName*、 *Password*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Source* |可选。 **变量型** 值，可以表示要由该 **Record** 对象表示的实体的 URL、 **Command** 、打开的 [Recordset](recordset-object-ado.md) 或其他 **Record** 对象，也可以表示包含 SQL SELECT 语句或表名的字符串。|
|*ActiveConnection* | 可选。 **变量型** 值，表示连接字符串或打开的 [Connection](connection-object-ado.md) 对象。|
|*Mode* |可选。[ConnectModeEnum](connectmodeenum.md) 值，其默认值为 **adModeUnknown** ，指定生成的 **Record** 对象的访问模式。|
|*CreateOptions* |可选。[RecordCreateOptionsEnum](recordcreateoptionsenum.md) 值，其默认值为 **adFailIfNotExists**，指定应打开现有的文件或目录，还是创建新文件或目录。如果设置为默认值，则从 [Mode](mode-property-ado.md) 属性获取访问模式。当 *Source* 参数不包含 URL 时忽略该参数。|
|*Options* |可选。[RecordOpenOptionsEnum](recordopenoptionsenum.md) 值，其默认值为 **adOpenRecordUnspecified** ，指定用于打开 **Record** 的选项。这些值可以组合使用。|
|*UserName* |可选。 包含用户 ID 的**字符串型**值，如果需要，授予访问 *Source* 的权限。|
|*Password* |可选。 包含密码的**字符串型**值，如果需要，将验证 *UserName*。|

## <a name="remarks"></a>注解

*Source* 可以是：

- URL。如果 URL 的协议为 HTTP，则默认情况下将调用 Internet 提供程序。如果 URL 指向的节点包含可执行脚本（如 .ASP 页），则默认情况下打开包含源（而不是执行的内容）的 **Record**。使用 *Options* 参数可修改此行为。

- **Record** 对象。从其他 **Record** 打开的 **Record** 对象将克隆原始 **Record** 对象。

- **Command** 对象。打开的 **Record** 对象代表通过执行 **Command** 返回的单个行。如果结果包含多个行，则将第一个行的内容放置在记录中，并且会向 **Errors** 集合添加一个错误。

- SQL SELECT 语句。打开的 **Record** 对象代表通过执行字符串的内容返回的单个行。如果结果包含多个行，则将第一个行的内容放置在记录中，并且会向 **Errors** 集合添加一个错误。

- 表名。

如果 **Record** 对象代表的实体无法通过 URL 访问（例如，从数据库派生的 **Recordset** 的某个行），则 [ParentURL](parenturl-property-ado.md) 属性的值和使用 **adRecordURL** 常量访问的字段的值都为 Null。

> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。


