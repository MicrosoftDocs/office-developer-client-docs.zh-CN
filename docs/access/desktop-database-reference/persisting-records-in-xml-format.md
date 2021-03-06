---
title: 以 XML 格式暂留记录
TOCTitle: Persisting records in XML format
ms:assetid: 8071e244-60c7-759c-094c-152add5d72e4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249545(v=office.15)
ms:contentKeyID: 48545924
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 10a5651c74580950810211c4f71e19fc80a16a95
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287564"
---
# <a name="persisting-records-in-xml-format"></a>以 XML 格式暂留记录

**适用于**：Access 2013、Office 2013

像 ADTG 格式一样，可以通过 Microsoft OLE DB Persistence Provider 用 XML 格式持久化 **Recordset** 。此提供程序可以从保存的 XML 文件或流（它们包含 ADO 生成的架构信息）生成仅向前的只读行集。同样，它可以处理 ADO **Recordset** ，然后生成 XML，并将它保存到文件或任何实现 COM **IStream** 接口的对象（实际上，文件只是支持 **IStream** 的对象的另一个示例）。对于 2.5 和更高版本，ADO 依赖于 Microsoft XML 语法分析程序 (MSXML) 来将 XML 加载到 **Recordset** 中；因此 msxml.dll 是必需的。对于 2.5 版本，这是 Internet Explorer 5 附带的 MSXML。对于 2.6 版本，则是 SQL Server 2000 附带的 MSXML。

> [!NOTE]
> [!注释] 在将分层 **Recordset** （数据定形）保存到 XML 格式时，有某些限制。如果分层 **Recordset** 包含挂起的更新，则无法保存到 XML，并且无法保存参数化分层 **Recordset** 。有关详细信息，请参阅 [XML 中的分层记录集](hierarchical-recordsets-in-xml.md)。


通过 ADO 将数据持久化到 XML 中并再次加载它的最容易方式是分别使用 **Save** 和 **Open** 方法。以下 ADO 代码示例演示了将 Titles 表中的数据保存到名为 titles.sav 的文件中。

```vb 
 
Dim rs as new Recordset 
Dim rs2 as new Recordset 
Dim c as new Connection 
Dim s as new Stream 
 
' Query the Titles table. 
c.Open "provider='sqloledb';data source='mydb';initial catalog='pubs';Integrated Security='SSPI'" 
rs.cursorlocation = adUseClient 
rs.Open "select * from titles", c, adOpenStatic 
 
' Save to the file in the XML format. Note that if you don't specify 
' adPersistXML, a binary format (ADTG) will be used by default. 
rs.Save "titles.sav", adPersistXML 
 
' Save the Recordset into the ADO Stream object. 
rs.save s, adPersistXML 
rs.Close 
c.Close 
 
set rs = nothing 
 
Reopen the file. 
rs.Open "titles.sav",,,,adCmdFile 
'Open the Stream back into a Recordset. 
rs2.open s 
```

ADO 始终持久化整个 **Recordset** 对象。 如果希望只持久化 **Recordset** 对象中行的子集，请使用 **Filter** 方法来筛选行或更改选择子句。 但是, 必须使用客户端游标 (**CursorLocation** = **adUseClient**) 打开**Recordset**对象, 才能使用**筛选器**方法保存行的子集。 例如，若要检索以字母"b"开头的标题，可以将筛选器应用于打开的 **Recordset** 对象：

```vb 
 
rs.Filter "title_id like 'B*'" 
rs.Save "btitles.sav", adPersistXML 
```

ADO 总是使用客户端游标引擎行集来产生可滚动、可标记书签的 **Recordset** 对象，而且生成的对象位于 Persistence Provider 所生成的仅向前数据的顶部。

本节包括下列主题：

- [XML 持久性格式](xml-persistence-format.md)

- [命名空间](namespaces.md)

- [架构部分](schema-section.md)

- [Data 节](data-section.md)

- [XML 中的层次记录集](hierarchical-recordsets-in-xml.md)

- [XML 中的记录集动态属性](recordset-dynamic-properties-in-xml.md)

- [XSLT 转换](xslt-transformations.md)

- [保存到 XML DOM 对象](saving-to-the-xml-dom-object.md)

- [XML 安全性注意事项](xml-security-considerations.md)

- [XML 记录集持久性方案主题](xml-recordset-persistence-scenario.md)
