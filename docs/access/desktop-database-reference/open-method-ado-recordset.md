---
title: Open 方法（ADO 记录集）
TOCTitle: Open method (ADO Recordset)
ms:assetid: 87ef19a4-28e1-dec7-ed33-4ae500b9c460
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249591(v=office.15)
ms:contentKeyID: 48546119
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e5f8dbdfa61a671e2efb9aac2596cfda5cd1727b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288404"
---
# <a name="open-method-ado-recordset"></a>Open 方法（ADO 记录集）

**适用于**：Access 2013、Office 2013

打开游标。

## <a name="syntax"></a>语法

*recordset*。Open*Source*、 *ActiveConnection*、 *CursorType*、 *LockType*、 *Options*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Source* |可选。 **变量型** ，取值为有效的 [Command](command-object-ado.md) 对象、SQL 语句、表名称、存储过程调用、URL 或包含永久存储 [Recordset](stream-object-ado.md) 的文件或 [Stream](recordset-object-ado.md) 对象的名称。|
|*ActiveConnection* |可选。取值为有效的 **Connection** 对象变量名称的 [变量型](connection-object-ado.md) ，或包含 **ConnectionString** 参数的 [字符串型](connectionstring-property-ado.md) 。|
|*CursorType* |可选。[CursorTypeEnum](cursortypeenum.md) 值，用于确定在打开 **Recordset** 时提供程序应使用的游标的类型。默认值为 **adOpenForwardOnly** 。|
|*LockType* |可选。[LockTypeEnum](locktypeenum.md) 值，用于确定在打开 **Recordset** 时提供程序应使用的锁定（并发）的类型。默认值为 **adLockReadOnly** 。|
|*Options* |可选。**长整型**值，指示当 *Source* 参数表示除 **Command** 对象之外的项时提供程序应如何计算该参数，或 **Recordset** 应从以前保存它的文件中还原。此参数可以是一个或多个 [CommandTypeEnum](commandtypeenum.md) 或 [ExecuteOptionEnum](executeoptionenum.md) 值，这些值可与位 AND 运算符结合使用。|

> [!NOTE]
> [!注释] 如果从包含持久性 **Recordset** 的 **Stream** 中打开 **Recordset** ，则使用 **adAsyncFetchNonBlocking** 的 **ExecuteOptionEnum** 值不起作用。提取和阻止将同步进行。

**adExecuteNoRecords** 或 **adExecuteStream** 的 **ExecuteOpenEnum** 值不应与 **Open** 一起使用。

## <a name="remarks"></a>注解

ADO **Recordset** 的默认游标是仅向前型只读游标，位于服务器上。

如果对 **Recordset** 对象使用 **Open** 方法，则会打开一个游标，该游标表示来自基表、查询结果或以前保存的 **Recordset** 的记录。

使用可选的 *Source* 参数可指定使用下列任一项目的数据源：**Command** 对象变量、SQL 语句、存储过程、表名称、URL 或完整的文件路径名。 如果*Source*是文件路径名称, 则可以是完整路径 ("c:\\dir\\file. rst"), 即相对路径 (".。。\\rst ") 或 URL ("https://files/file.rst")。

最好不要使用 **Open** 方法的 *Source* 参数执行不返回记录的操作查询，因为很难确定调用是否成功。这种查询返回的 **Recordset** 将被关闭。可以改为调用 **Command** 对象的 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 方法或 **Connection** 对象的 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-connection) 方法来执行不返回记录的查询（如 SQL INSERT 语句）。

*ActiveConnection* 参数对应于 [ActiveConnection](activeconnection-property-ado.md) 属性，并指定在哪个连接中打开 **Recordset** 对象。 如果传递此参数的连接定义，ADO 将使用指定的参数打开新连接。 使用客户端游标 (**CursorLocation** = **adUseClient**) 打开**Recordset**后, 可以更改此属性的值, 以将更新发送到另一个提供程序。 也可以将此属性设置为 **Nothing**（在 Microsoft Visual Basic 中）或 NULL，以使 **Recordset** 与任何提供程序断开连接。 但是，更改服务器端游标的 **ActiveConnection** 将生成错误。

对于直接对应于 **Recordset** 对象属性（*Source*、*CursorType* 和 *LockType*）的其他参数，参数与属性的关系如下所示：

- 打开 **Recordset** 对象之前，属性处于读/写状态。

- 除非执行 **Open** 方法时传递相应的参数，否则不使用属性设置。如果传递参数，则它会替代相应的属性设置，并用参数值更新该属性设置。

- 打开 **Recordset** 对象之后，这些属性变为只读。

> [!NOTE]
> **ActiveConnection** 属性仅对于 [Source](source-property-ado-recordset.md) 属性被设置为有效 **Command** 对象的那些 **Recordset** 对象为只读，即使 **Recordset** 对象未打开也是如此。

如果在 *Source* 参数中传递 **Command** 对象，并且还传递 *ActiveConnection* 参数，则会发生错误。**Command** 对象的 **ActiveConnection** 属性必须事先已设置为有效的 **Connection** 对象或连接字符串。

在 *Source* 参数中传递除 **Command** 对象之外的其他内容时，可以使用 *Options* 参数优化 *Source* 参数的取值。如果 *Options* 参数未定义，则 ADO 必须调用提供程序来确定该参数是 SQL 语句、存储过程、URL 还是表名称，因此性能可能会下降。如果知道所使用的 *Source* 类型，可以设置 *Options* 参数指示 ADO 直接跳转到相关的代码。如果 *Options* 参数与 *Source* 类型不匹配，则会发生错误。

如果在 *Source* 参数中传递 **Stream** 对象，则不应将信息传递给其他参数，否则会产生错误。从 **Stream** 打开 **Recordset** 时，**ActiveConnection** 信息不会保留。

如果 **Recordset** 没有相关联的连接，则 *Options* 参数的默认值为 **adCmdFile**。永久存储的 **Recordset** 对象通常属于这种情况。

如果数据源不返回任何记录，则提供程序同时将 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性设置为 **True** ，且不定义当前记录的位置。如果游标类型允许，仍可以在此空 **Recordset** 对象中添加新数据。

结束对打开的 **Recordset** 对象的操作时，请使用 [Close](close-method-ado.md) 方法释放所有关联的系统资源。关闭对象不会将其从内存中删除，您可以更改其属性设置，以后使用 **Open** 方法重新打开对象。若要将对象从内存中彻底删除，请将对象变量设置为 *Nothing*。

在设置**ActiveConnection**属性之前, 调用**Open** with no 操作数, 以创建通过将字段追加到**recordset** [fields](fields-collection-ado.md)集合中而创建的**recordset**的实例。

如果已将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient**，则可以使用以下两种方法之一以异步方式检索行。 建议的方法是将 *Options* 设置为 **adAsyncFetch**。 另外，也可以使用 [Properties](properties-collection-ado.md) 集合中的"Asynchronous Rowset Processing"动态属性，但如果不将 **Options** 参数设置为 **adAsyncFetch** ，相关的检索事件就有可能丢失。

> [!NOTE]
> 只能通过 **Open** 方法的 *Options* 参数来支持 MS 远程提供程序中的后台提取功能。

> [!NOTE]
> [!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。 有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。


