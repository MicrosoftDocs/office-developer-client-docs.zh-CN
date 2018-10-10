---
title: Open 方法 (ADO Recordset)
TOCTitle: Open Method (ADO Recordset)
ms:assetid: 87ef19a4-28e1-dec7-ed33-4ae500b9c460
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249591(v=office.15)
ms:contentKeyID: 48546119
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c6887770c8e0c3b98b6ff990c884c5325d6ce6d3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468391"
---
# <a name="open-method-ado-recordset"></a>Open 方法 (ADO Recordset)


**适用于**： Access 2013 |Office 2013


打开游标。

## <a name="syntax"></a>语法

*记录集*。打开*源*、 *ActiveConnection*、 *CursorType*、 *LockType*、*选项*

## <a name="parameters"></a>参数

  - *Source*

  - 可选。 **变量型** ，取值为有效的 [Command](command-object-ado.md) 对象、SQL 语句、表名称、存储过程调用、URL 或包含永久存储 [Recordset](stream-object-ado.md) 的文件或 [Stream](recordset-object-ado.md) 对象的名称。

  - *ActiveConnection*

  - 可选。取值为有效的 **Connection** 对象变量名称的 [变量型](connection-object-ado.md) ，或包含 **ConnectionString** 参数的 [字符串型](connectionstring-property-ado.md) 。

  - *CursorType*

  - 可选。[CursorTypeEnum](cursortypeenum.md) 值，用于确定在打开 **Recordset** 时提供程序应使用的游标的类型。默认值为 **adOpenForwardOnly** 。

  - *LockType*

  - 可选。[LockTypeEnum](locktypeenum.md) 值，用于确定在打开 **Recordset** 时提供程序应使用的锁定（并发）的类型。默认值为 **adLockReadOnly** 。

  - *Options*

  - 可选。 **Long**值，该值指示如何提供程序应评估*Source*参数之后，如果之外的**Command**对象，它表示或应从先前已保存的文件还原**Recordset** 。 此参数可以是一个或多个 [CommandTypeEnum](commandtypeenum.md) 或 [ExecuteOptionEnum](executeoptionenum.md) 值，这些值可与位 AND 运算符结合使用。


> [!NOTE]
> <P>[!注释] 如果从包含持久性 <STRONG>Recordset</STRONG> 的 <STRONG>Stream</STRONG> 中打开 <STRONG>Recordset</STRONG> ，则使用 <STRONG>adAsyncFetchNonBlocking</STRONG> 的 <STRONG>ExecuteOptionEnum</STRONG> 值不起作用。提取和阻止将同步进行。</P>



**adExecuteNoRecords** 或 **adExecuteStream** 的 **ExecuteOpenEnum** 值不应与 **Open** 一起使用。

## <a name="remarks"></a>备注

ADO **Recordset** 的默认游标是仅向前型只读游标，位于服务器上。

如果对 **Recordset** 对象使用 **Open** 方法，则会打开一个游标，该游标表示来自基表、查询结果或以前保存的 **Recordset** 的记录。

使用可选的*源*参数指定数据源使用下列选项之一：**命令**对象变量、 SQL 语句、 存储的过程、 表名称、 URL 或完整文件路径名称。 如果*源*是文件路径名称，它可以是完整路径 ("c:\\dir\\file.rst")，相对路径 ("...\\file.rst")，或者是 URL ("https://files/file.rst")。

不建议使用**Open**方法的*Source*参数执行的操作查询，因为没有任何轻松确定呼叫是否成功，则不返回记录。 这种查询返回的 **Recordset** 将被关闭。 可以改为调用 [Command](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 对象的 **Execute** 方法或 [Connection](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 对象的 **Execute** 方法来执行不返回记录的查询（如 SQL INSERT 语句）。

*ActiveConnection*参数对应于[ActiveConnection](activeconnection-property-ado.md)属性，并指定在哪个连接来打开**Recordset**对象。 如果传递此参数的连接定义，ADO 将使用指定的参数打开新连接。 与客户端游标打开**Recordset**后 (**CursorLocation** = **adUseClient**)，您可以更改此属性以将更新发送到其他提供程序的值。 也可以将此属性设置为 **Nothing** （在 Microsoft Visual Basic 中）或 NULL，以使 **Recordset** 与任何提供程序断开连接。 但是，更改服务器端游标的 **ActiveConnection** 将生成错误。

对于直接对应于 **Recordset** 对象属性（*Source*、*CursorType* 和 *LockType*）的其他参数，参数与属性的关系如下所示：

  - 打开 **Recordset** 对象之前，属性处于读/写状态。

  - 除非执行 **Open** 方法时传递相应的参数，否则不使用属性设置。如果传递参数，则它会替代相应的属性设置，并用参数值更新该属性设置。

  - 打开 **Recordset** 对象之后，这些属性变为只读。


> [!NOTE]
> <P>[!注释] <STRONG>ActiveConnection</STRONG> 属性仅对于 <STRONG>Source</STRONG> 属性被设置为有效 <A href="source-property-ado-recordset.md">Command</A> 对象的那些 <STRONG>Recordset</STRONG> 对象为只读，即使 <STRONG>Recordset</STRONG> 对象未打开也是如此。</P>



如果*源*参数中传递的**Command**对象，并且还传递*ActiveConnection*参数，将发生错误。 **Command** 对象的 **ActiveConnection** 属性必须事先已设置为有效的 **Connection** 对象或连接字符串。

如果*源*参数中传递的**Command**对象以外的内容，可以使用*Options*参数来优化评估*源*参数。 如果未定义*Options*参数，您可能会遇到降低的性能，因为 ADO 必须进行到提供程序的调用，以确定是否的 SQL 语句、 存储的过程、 URL 或表名称参数。 如果您知道哪些*源*类型您使用的，设置在*Options*参数指示 ADO 直接跳转到了相关代码。 如果在*Options*参数与*源*类型不匹配，将发生错误。

如果*源*参数中传递**Stream**对象，您不应将信息传递到其他参数。 这样将生成一个错误。 从**流**中打开**Recordset**时，不会保留**ActiveConnection**信息。

*Options*参数的默认值是**adCmdFile** ，如果没有连接与**记录集**相关联。 永久存储的 **Recordset** 对象通常属于这种情况。

如果数据源不返回任何记录，则提供程序同时将 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性设置为 **True** ，且不定义当前记录的位置。如果游标类型允许，仍可以在此空 **Recordset** 对象中添加新数据。

结束对打开的 **Recordset** 对象的操作时，请使用 [Close](close-method-ado.md) 方法释放所有关联的系统资源。关闭对象不会将其从内存中删除，您可以更改其属性设置，以后使用 **Open** 方法重新打开对象。若要将对象从内存中彻底删除，请将对象变量设置为 *Nothing*。

在设置**ActiveConnection**属性之前，则调用**Open**没有操作数以创建通过向**Recordset** [Fields](fields-collection-ado.md)集合追加字段创建的**Recordset**的实例。

如果已将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** ，则可以使用以下两种方法之一以异步方式检索行。 推荐的方法是将*选项*设置为**adAsyncFetch**。 另外，也可以使用 [Properties](properties-collection-ado.md) 集合中的"Asynchronous Rowset Processing"动态属性，但如果不将 **Options** 参数设置为 **adAsyncFetch** ，相关的检索事件就有可能丢失。


> [!NOTE]
> <P>MS 远程提供程序中的后台提取功能仅支持通过<STRONG>Open</STRONG>方法的<EM>Options</EM>参数。</P>




> [!NOTE]
> <P>[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</P>


