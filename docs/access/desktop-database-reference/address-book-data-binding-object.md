---
title: 通讯簿数据绑定对象
TOCTitle: Address Book Data-Binding object
ms:assetid: cf43f645-1ee1-8655-eb70-86d601e9f3f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250030(v=office.15)
ms:contentKeyID: 48547807
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7fb5302d1c2b8e4eebb6dbe1a5906459834b8e41
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281865"
---
# <a name="address-book-data-binding-object"></a>通讯簿数据绑定对象


**适用于**：Access 2013、Office 2013

"通讯簿"应用程序使用 [RDS.DataControl](datacontrol-object-rds.md) 对象将 SQL Server 数据库中的数据绑定到应用程序客户端 HTML 页中的可视化对象（在此例中为 DHTML 表）。事件驱动的 VBScript 程序逻辑使用 [RDS.DataControl](datacontrol-object-rds.md) 执行以下操作：

  - 查询数据库、发送对数据库的更新和刷新数据网格。

  - 允许用户在数据网格中移动到第一个、下一个、上一个或最后一个记录。

以下代码定义了 **RDS.DataControl** 组件：

```vb 
 
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" 
   ID=DC1 Width=1 Height=1> 
   <PARAM NAME="SERVER" VALUE="https://<%=Request.ServerVariables("SERVER_NAME")%>"> 
   <PARAM NAME="CONNECT" VALUE="Provider=sqloledb; 
Initial Catalog=AddrBookDb;Integrated Security=SSPI;"> 
</OBJECT> 
```

OBJECT 标记用于定义程序中的 **RDS.DataControl** 组件。此标记包括以下两种类型的参数：

  - 与通用 OBJECT 标记关联的参数。

  - 特定于 **RDS.DataControl** 对象的参数。

## <a name="generic-object-tag-parameters"></a>通用 OBJECT 标记参数

下表列出了与 OBJECT 标记关联的参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>描述</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><em>CLASSID</em></strong></p></td>
<td><p>唯一，128 位数字，用于标识嵌入系统的对象类型。此标识符保存在本地计算机的系统注册表中。（有关 <strong>RDS.DataControl</strong> 对象的类 ID 的信息，请参阅 <a href="datacontrol-object-rds.md">RDS.DataControl 对象</a>。）</p></td>
</tr>
<tr class="even">
<td><p><strong><em>号</em></strong></p></td>
<td><p>为嵌入对象定义文档范围内的标识符，以便在代码中标识该对象。</p></td>
</tr>
</tbody>
</table>


## <a name="rdsdatacontrol-tag-parameters"></a>RDS.DataControl 标记参数

下表介绍特定于 **RDS.DataControl** 对象的参数。（有关 **RDS.DataControl** 对象参数的完整列表以及使用这些参数的场合，请参阅 [RDS.DataControl 对象](datacontrol-object-rds.md)。）

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>描述</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="server-property-rds.md">服务器主板</a></p></td>
<td><p>如果使用的是 HTTP, 则值是服务器计算机的名称, 后跟 https://。</p></td>
</tr>
<tr class="even">
<td><p><a href="connect-property-rds.md">连接</a></p></td>
<td><p>提供 <strong>RDS.DataControl</strong> 连接到 SQL Server 的必要连接信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/sql-property-ado">SQL</a></p></td>
<td><p>设置或返回用于检索 <a href="recordset-object-ado.md">Recordset</a> 的查询字符串。</p></td>
</tr>
</tbody>
</table>

