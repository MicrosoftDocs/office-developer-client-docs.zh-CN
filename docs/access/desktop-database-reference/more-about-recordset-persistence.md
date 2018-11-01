---
title: 关于记录集持久化的详细信息
TOCTitle: More About Recordset Persistence
ms:assetid: f3248de7-6eef-1dd0-ff96-557b411789e7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250232(v=office.15)
ms:contentKeyID: 48548666
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: baf1e4976b9669deed0a80f6405127afc88d521e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878289"
---
# <a name="more-about-recordset-persistence"></a>关于记录集持久化的详细信息


**适用于**： Access 2013、 Office 2013

ADO 记录集对象支持使用其 **Save** 方法将 [Recordset](save-method-ado.md) 对象的内容存储在文件中。 在本地驱动器上，网络服务器，或在网站上的 URL，可能存在的永久存储的文件。 随后，可以用 **Recordset** 对象的 [Open](open-method-ado-recordset.md) 方法或 [Connection](connection-object-ado.md) 对象的 [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 方法还原该文件。

此外，[GetString](getstring-method-ado.md) 方法可以将 **Recordset** 对象转换为以指定的字符分隔的列和行的形式。

若要持久化 **Recordset** ，请首先将它转换为可以存储在文件中的形式。可以用专用的 Advanced Data TableGram (ADTG) 格式或开放的可扩展标记语言 (XML) 格式来存储 **Recordset** 对象。下面显示了 ADTG 示例。有关 XML 持久化的详细信息，请参阅 [用 XML 格式持久化记录](persisting-records-in-xml-format.md)。

应当将任何挂起的更改保存在持久化文件中。这将允许您发出返回 **Recordset** 对象的查询，编辑 **Recordset** ，保存记录集和挂起的更改、随后还原 **Recordset** ，然后用保存的挂起更改来更新数据源。

有关永久存储 **Stream** 对象的信息，请参阅第 10 章中的 [流和持久化](streams-and-persistence.md)。

有关 **Recordset** 持久化的示例，请参阅 [XML Recordset 持久化方案](xml-recordset-persistence-scenario.md)。

## <a name="example"></a>示例

**保存记录集：**

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Save "c:\yourFile.adtg", adPersistADTG 
```

**用 Recordset.Open 打开持久化文件：**

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "c:\yourFile.adtg", "Provider='MSPersist'",,,adCmdFile
```

或者，如果 **Recordset** 没有活动连接，则可以接受所有默认值，只需编码如下：

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "c:\yourFile.adtg" 
```

**使用 Connection.Execute 打开持久化文件：**

```vb 
 
Dim conn as New ADODB.Connection 
Dim rs as ADODB.Recordset 
conn.Open "Provider='MSPersist'" 
Set rs = conn.execute("c:\yourFile.adtg") 
```

**使用 RDS.DataControl 打开持久化文件：**

这种情况下，不设置 **Server** 属性。

```vb 
 
Dim dc as New RDS.DataControl 
dc.Connection = "Provider='MSPersist'" 
dc.SQL = "c:\yourFile.adtg" 
dc.Refresh
```

