---
title: Microsoft OLE DB Provider for Microsoft Active Directory Service
TOCTitle: Microsoft OLE DB Provider for Microsoft Active Directory Service
ms:assetid: 92d1c967-aa61-f3b5-1c0a-301ef236894c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249647(v=office.15)
ms:contentKeyID: 48546385
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c1555883ef8305225d6ddd1969d98de082288a6b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887535"
---
# <a name="microsoft-ole-db-provider-for-microsoft-active-directory-service"></a>Microsoft OLE DB Provider for Microsoft Active Directory Service

**适用于**： Access 2013、 Office 2013

Microsoft Active Directory Service Interfaces (ADSI) 提供程序允许 ADO 通过 ADSI 连接到各种异构目录服务。这样，除可以访问任何 LDAP 兼容目录服务和 Novell 目录服务外，还为 ADO 应用程序提供了对 Microsoft Windows NT 4.0 和 Microsoft Windows 2000 目录服务的只读访问权限。ADSI 本身就基于一个提供程序模型，因此，如果有一个新的提供程序提供了对其他目录的访问权限，ADO 应用程序就可以对该目录进行无缝访问。ADSI 提供程序为自由线程且支持 Unicode。

## <a name="connection-string-parameters"></a>连接字符串参数

若要连接到此提供程序，请将 **ConnectionString** 属性的 [Provider](connectionstring-property-ado.md) 参数设置为：

```vb 
 
ADSDSOObject 
```

读取 [Provider](provider-property-ado.md) 属性时，也会返回此字符串。

## <a name="typical-connection-string"></a>典型的连接字符串

此提供程序典型的连接字符串为：

```vb 
 
"Provider=ADSDSOObject;User ID=userName;Password=userPassword;" 
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
<td><p>指定 Microsoft OLE DB Provider for Microsoft Active Directory Service。</p></td>
</tr>
<tr class="even">
<td><p><strong>User ID</strong></p></td>
<td><p>指定用户名。如果忽略此关键字，则使用当前的登录用户名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Password</strong></p></td>
<td><p>指定用户密码。如果忽略此关键字，则使用当前的登录密码。</p></td>
</tr>
</tbody>
</table>


**命令文本**

该提供程序采用以下语法识别包含四个部分的命令文本字符串：

`"Root; Filter; Attributes[; Scope]"`

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>根</em></p></td>
<td><p>指示搜索开始的 <strong>ADsPath</strong> 对象（即搜索的根目录）。</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>指示采用 RFC 1960 格式的搜索筛选器。</p></td>
</tr>
<tr class="odd">
<td><p><em>Attributes</em></p></td>
<td><p>指示要返回的以逗号分隔的属性列表。</p></td>
</tr>
<tr class="even">
<td><p><em>Scope</em></p></td>
<td><p>可选。 指定搜索的作用域的<strong>字符串</strong>。 可以是下列选项之一： 基本 — 搜索基对象 （搜索的根）。<br />
OneLevel — Search 只有一个级别。<br />
子树 — 搜索整个子树。</p></td>
</tr>
</tbody>
</table>


例如：

```vb 
 
"<LDAP://DC=ArcadiaBay,DC=COM>;(objectClass=*);sn, givenName; subtree" 
```

该提供程序还支持命令文本使用 SQL SELECT。例如：

```vb 
 
"SELECT title, telephoneNumber From 'LDAP://DC=Microsoft, DC=COM' WHERE 
objectClass='user' AND objectCategory='Person'" 
```

该提供程序不会接受存储过程调用或简单的表名称（例如，[CommandType](commandtype-property-ado.md) 属性将始终为 **adCmdText**）。有关命令文本元素的更完整的说明，请参阅 Active Directory Service Interfaces 文档。

## <a name="recordset-behavior"></a>Recordset 行为

下面的表列出了使用此提供程序打开的 [Recordset](recordset-object-ado.md) 对象上可用的功能。 仅静态游标类型 (**为 adOpenStatic**) 才可用。

有关提供程序配置的 **Recordset** 行为的详细信息，请运行 [Supports](supports-method-ado.md) 方法并枚举 [Recordset](properties-collection-ado.md) 的 **Properties** 集合，以确定提供程序特定的动态属性是否存在。

标准 ADO **Recordset** 属性的可用性：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>属性</p></th>
<th><p>可用性</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="absolutepage-property-ado.md">AbsolutePage</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="absoluteposition-property-ado.md">AbsolutePosition</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="activeconnection-property-ado.md">ActiveConnection</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="bof-eof-properties-ado.md">BOF</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="bookmark-property-ado.md">Bookmark</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="cachesize-property-ado.md">CacheSize</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="cursorlocation-property-ado.md">CursorLocation</a></p></td>
<td><p>始终为 <strong>adUseServer</strong></p></td>
</tr>
<tr class="even">
<td><p><a href="cursortype-property-ado.md">CursorType</a></p></td>
<td><p>始终为 <strong>adOpenStatic</strong></p></td>
</tr>
<tr class="odd">
<td><p><a href="editmode-property-ado.md">EditMode</a></p></td>
<td><p>始终为 <strong>adEditNone</strong></p></td>
</tr>
<tr class="even">
<td><p><a href="bof-eof-properties-ado.md">EOF</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><a href="filter-property-ado.md">Filter</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="even">
<td><p><a href="locktype-property-ado.md">LockType</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="marshaloptions-property-ado.md">MarshalOptions</a></p></td>
<td><p>暂无</p></td>
</tr>
<tr class="even">
<td><p><a href="maxrecords-property-ado.md">MaxRecords</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="pagecount-property-ado.md">PageCount</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="pagesize-property-ado.md">PageSize</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="recordcount-property-ado.md">RecordCount</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="source-property-ado-recordset.md">Source</a></p></td>
<td><p>读/写</p></td>
</tr>
<tr class="odd">
<td><p><a href="state-property-ado.md">State</a></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><a href="status-property-ado-recordset.md">Status</a></p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


标准 ADO **Recordset** 方法的可用性：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>方法</p></th>
<th><p>是否可用</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="addnew-method-ado.md">AddNew</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="cancel-method-ado.md">Cancel</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><a href="cancelbatch-method-ado.md">CancelBatch</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="cancelupdate-method-ado.md">CancelUpdate</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><a href="clone-method-ado.md">Clone</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="close-method-ado.md">Close</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="delete-method-ado-recordset.md">Delete</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="getrows-method-ado.md">GetRows</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="move-method-ado.md">移动</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveFirst</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveLast</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MoveNext</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="movefirst-movelast-movenext-and-moveprevious-methods-ado.md">MovePrevious</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="nextrecordset-method-ado.md">NextRecordset</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="open-method-ado-recordset.md">Open</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="requery-method-ado.md">Requery</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="resync-method-ado.md">Resync</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p><a href="supports-method-ado.md">支持</a></p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p><a href="update-method-ado.md">更新</a></p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><a href="updatebatch-method-ado.md">UpdateBatch</a></p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>

