---
title: ActiveConnection 属性 (ADO)
TOCTitle: ActiveConnection property (ADO)
ms:assetid: 5501b2d7-b62c-5fff-1edd-2b7efb3f8c4a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249281(v=office.15)
ms:contentKeyID: 48544918
ms.date: 10/17/2018
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231115
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 037ae753f427c42f147972170dbb2e645b260623
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282528"
---
# <a name="activeconnection-property-ado"></a>ActiveConnection 属性 (ADO)

**适用于**：Access 2013、Office 2013

指示指定的 [Command](connection-object-ado.md)、[Recordset](command-object-ado.md) 或 [Record](recordset-object-ado.md) 对象当前属于哪个 [Connection](record-object-ado.md) 对象。

## <a name="settings-and-return-values"></a>设置和返回值

如果某个连接处于关闭状态，则设置或返回一个 **String** 值，其中包含该连接的定义；如果某个连接处于打开状态，则设置或返回一个 **Variant** ，其中包含当前的 **Connection** 对象。默认值为一个空对象引用。请参阅 [ConnectionString](connectionstring-property-ado.md) 属性。

## <a name="remarks"></a>注解

使用 **ActiveConnection** 属性可以确定 **Connection** 对象，通过该对象将执行指定的 **Command** 对象或打开指定的 **Recordset**。

### <a name="command"></a>Command

对于 **Command** 对象，**ActiveConnection** 属性为读/写属性。

如果在将此属性设置为打开的 [Connection](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 对象或有效的连接字符串前，尝试对 **Command** 对象调用 **Execute** 方法，则将发生错误。

**Microsoft Visual Basic**: 将**ActiveConnection**属性设置为*Nothing*将**Command**对象与当前**连接**解除关联, 并使提供程序释放数据上的任何关联资源源. 然后可以将 **Command** 对象与同一个或另一个 **Connection** 对象关联。 某些提供程序允许您将属性设置从一个**连接**更改为另一个, 而无需先将该属性设置为*Nothing*。

如果 **Command** 对象的 [Parameters](parameters-collection-ado.md) 集合包含提供程序提供的参数，并且将 **ActiveConnection** 属性设置为 *Nothing* 或另一个 **Connection** 对象，则会清除该集合。如果手动创建 [Parameter](parameter-object-ado.md) 对象，然后用它们填充 **Command** 对象的 **Parameters** 集合，则将 **ActiveConnection** 属性设置为 *Nothing* 或另一个 **Connection** 对象不会更改 **Parameters** 集合的内容。

如果将与 **Command** 对象关联的 **Connection** 对象关闭，则会将 **ActiveConnection** 属性设置为 *Nothing*。将此属性设置为已关闭的 **Connection** 对象将生成错误。

### <a name="recordset"></a>Recordset

对于打开的 **Recordset** 对象或其 **Source** 属性设置为有效 [Command](source-property-ado-recordset.md) 对象的 **Recordset** 对象， **ActiveConnection** 属性为只读属性。否则，该属性为读/写属性。

可以将此属性设置为有效的 **Connection** 对象或有效的连接字符串。在这种情况下，提供程序将使用此定义创建一个新 **Connection** 对象，并打开该连接。此外，提供程序还可能将此属性设置为新 **Connection** 对象，以便提供访问 **Connection** 对象获得扩展错误消息或执行其他命令的方式。

如果使用 [Open](open-method-ado-recordset.md) 方法的 *ActiveConnection* 参数打开 **Recordset** 对象，**ActiveConnection** 属性将继承该参数的值。

如果将 **Recordset** 对象的 **Source** 属性设置为有效的 **Command** 对象变量，**Recordset** 的 **ActiveConnection** 属性将继承 **Command** 对象的 **ActiveConnection** 属性的设置。

**远程数据服务用法**: 当在客户端 Recordset 对象上使用时, 只能将此属性设置为连接字符串或 (在 Microsoft Visual basic 或 Visual basic 脚本版中) 为*Nothing*。

### <a name="record"></a>Record

当 **Record** 对象关闭时此属性为可读/写属性，可以包含连接字符串或对打开的 **Connection** 对象的引用。当 **Record** 对象打开时，此属性为只读属性且包含对打开的 **Connection** 对象的引用。

当从 URL 打开 **Record** 对象时，会隐式地创建一个 **Connection** 对象。 通过将该 **Connection** 对象分配给此属性，或在 **Open** 方法调用中使用 **Connection** 对象作为参数，可以使用现有的已打开的 **Connection** 对象打开 [Record](open-method-ado-record.md) 。 如果该**记录**是从现有的**记录**或[recordset](recordset-object-ado.md)打开的, 它将自动与该**record**或**recordset**对象的**Connection**对象相关联。

> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。



