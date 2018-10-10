---
title: Microsoft OLE DB Provider for Oracle
TOCTitle: Microsoft OLE DB Provider for Oracle
ms:assetid: 97508e3f-077f-9b85-f4dd-8dd01a201aba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249674(v=office.15)
ms:contentKeyID: 48546465
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6b4a8847dd7c96813cec6bd8a9868bc9a92b0d2a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467274"
---
# <a name="microsoft-ole-db-provider-for-oracle"></a>Microsoft OLE DB Provider for Oracle

**适用于**： Access 2013 |Office 2013

Microsoft OLE DB Provider for Oracle 允许 ADO 访问 Oracle 数据库。

## <a name="connection-string-parameters"></a>连接字符串参数

若要连接到此提供程序，请将 *ConnectionString* 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：

```vb 
 
MSDAORA 
```

读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。

如果在 Oracle 数据库中执行包含键集或动态游标的连接查询，则将发生错误。Oracle 仅支持静态的只读游标。

## <a name="typical-connection-string"></a>典型的连接字符串

此提供程序典型的连接字符串为：

```vb 
 
"Provider=MSDAORA;Data Source=serverName;User ID=userName; Password=userPassword;" 
```

该字符串由以下关键字组成：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>关键字</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Provider</strong></p></td>
<td><p>指定 OLE DB Provider for Oracle。</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Source</strong></p></td>
<td><p>指定服务器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>User ID</strong></p></td>
<td><p>指定用户名。</p></td>
</tr>
<tr class="even">
<td><p><strong>Password</strong></p></td>
<td><p>指定用户密码。</p></td>
</tr>
</tbody>
</table>


## <a name="provider-specific-connection-parameters"></a>提供程序特定的连接参数

除了支持 ADO 定义的那些参数以外，该提供程序还支持几个提供程序特定的连接参数。与 ADO 连接属性一样，可以通过 [Connection](properties-collection-ado.md) 对象的 [Properties](connection-object-ado.md) 集合或将其作为 **ConnectionString** 的一部分来设置这些提供程序特定的属性。

这些参数在《OLE DB 程序员参考》中进行了全面介绍（[ADO 动态属性索引](ado-dynamic-property-index.md)提供了这些参数名与对应的 OLE DB 属性之间的交叉引用）。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Window Handle</strong></p></td>
<td><p>指示用于提示附加信息的窗口句柄。</p></td>
</tr>
<tr class="even">
<td><p><strong>Locale Identifier</strong></p></td>
<td><p>指示唯一的 32 位数字（例如 1033），指定与用户的语言有关的首选项。这些首选项指示设置日期和时间格式的方式、按字母顺序对项排序的方式、比较字符串的方式等。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OLE DB Services</strong></p></td>
<td><p>指示用于指定启用或禁用的各项 OLE DB 服务的位掩码。</p></td>
</tr>
<tr class="even">
<td><p><strong>Prompt</strong></p></td>
<td><p>指示在建立连接时是否提示用户。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extended Properties</strong></p></td>
<td><p>包含提供程序特定的扩展连接信息的字符串。仅对提供程序特定的连接信息（不能通过属性机制描述）使用此属性。</p></td>
</tr>
</tbody>
</table>

