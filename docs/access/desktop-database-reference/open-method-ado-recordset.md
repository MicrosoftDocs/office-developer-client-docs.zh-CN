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
# <a name="open-method-ado-recordset"></a><span data-ttu-id="96dfa-102">Open 方法 (ADO Recordset)</span><span class="sxs-lookup"><span data-stu-id="96dfa-102">Open Method (ADO Recordset)</span></span>


<span data-ttu-id="96dfa-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="96dfa-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="96dfa-104">打开游标。</span><span class="sxs-lookup"><span data-stu-id="96dfa-104">Opens a cursor.</span></span>

## <a name="syntax"></a><span data-ttu-id="96dfa-105">语法</span><span class="sxs-lookup"><span data-stu-id="96dfa-105">Syntax</span></span>

<span data-ttu-id="96dfa-106">*记录集*。打开*源*、 *ActiveConnection*、 *CursorType*、 *LockType*、*选项*</span><span class="sxs-lookup"><span data-stu-id="96dfa-106">*recordset*.Open*Source*, *ActiveConnection*, *CursorType*, *LockType*, *Options*</span></span>

## <a name="parameters"></a><span data-ttu-id="96dfa-107">参数</span><span class="sxs-lookup"><span data-stu-id="96dfa-107">Parameters</span></span>

  - <span data-ttu-id="96dfa-108">*Source*</span><span class="sxs-lookup"><span data-stu-id="96dfa-108">*Source*</span></span>

  - <span data-ttu-id="96dfa-p101">可选。 **变量型** ，取值为有效的 [Command](command-object-ado.md) 对象、SQL 语句、表名称、存储过程调用、URL 或包含永久存储 [Recordset](stream-object-ado.md) 的文件或 [Stream](recordset-object-ado.md) 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p101">Optional. A **Variant** that evaluates to a valid [Command](command-object-ado.md) object, an SQL statement, a table name, a stored procedure call, a URL, or the name of a file or [Stream](stream-object-ado.md) object containing a persistently stored [Recordset](recordset-object-ado.md).</span></span>

  - <span data-ttu-id="96dfa-111">*ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="96dfa-111">*ActiveConnection*</span></span>

  - <span data-ttu-id="96dfa-p102">可选。取值为有效的 **Connection** 对象变量名称的 [变量型](connection-object-ado.md) ，或包含 **ConnectionString** 参数的 [字符串型](connectionstring-property-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p102">Optional. Either a **Variant** that evaluates to a valid [Connection](connection-object-ado.md) object variable name, or a **String** that contains [ConnectionString](connectionstring-property-ado.md) parameters.</span></span>

  - <span data-ttu-id="96dfa-114">*CursorType*</span><span class="sxs-lookup"><span data-stu-id="96dfa-114">*CursorType*</span></span>

  - <span data-ttu-id="96dfa-p103">可选。[CursorTypeEnum](cursortypeenum.md) 值，用于确定在打开 **Recordset** 时提供程序应使用的游标的类型。默认值为 **adOpenForwardOnly** 。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p103">Optional. A [CursorTypeEnum](cursortypeenum.md) value that determines the type of cursor that the provider should use when opening the **Recordset**. The default value is **adOpenForwardOnly**.</span></span>

  - <span data-ttu-id="96dfa-118">*LockType*</span><span class="sxs-lookup"><span data-stu-id="96dfa-118">*LockType*</span></span>

  - <span data-ttu-id="96dfa-p104">可选。[LockTypeEnum](locktypeenum.md) 值，用于确定在打开 **Recordset** 时提供程序应使用的锁定（并发）的类型。默认值为 **adLockReadOnly** 。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p104">Optional. A [LockTypeEnum](locktypeenum.md) value that determines what type of locking (concurrency) the provider should use when opening the **Recordset**. The default value is **adLockReadOnly**.</span></span>

  - <span data-ttu-id="96dfa-122">*Options*</span><span class="sxs-lookup"><span data-stu-id="96dfa-122">*Options*</span></span>

  - <span data-ttu-id="96dfa-123">可选。</span><span class="sxs-lookup"><span data-stu-id="96dfa-123">Optional.</span></span> <span data-ttu-id="96dfa-124">**Long**值，该值指示如何提供程序应评估*Source*参数之后，如果之外的**Command**对象，它表示或应从先前已保存的文件还原**Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="96dfa-124">A **Long** value that indicates how the provider should evaluate the *Source* argument if it represents something other than a **Command** object, or that the **Recordset** should be restored from a file where it was previously saved.</span></span> <span data-ttu-id="96dfa-125">此参数可以是一个或多个 [CommandTypeEnum](commandtypeenum.md) 或 [ExecuteOptionEnum](executeoptionenum.md) 值，这些值可与位 AND 运算符结合使用。</span><span class="sxs-lookup"><span data-stu-id="96dfa-125">Can be one or more [CommandTypeEnum](commandtypeenum.md) or [ExecuteOptionEnum](executeoptionenum.md) values, which can be combined with a bitwise AND operator.</span></span>


> [!NOTE]
> <P><span data-ttu-id="96dfa-126">[!注释] 如果从包含持久性 <STRONG>Recordset</STRONG> 的 <STRONG>Stream</STRONG> 中打开 <STRONG>Recordset</STRONG> ，则使用 <STRONG>adAsyncFetchNonBlocking</STRONG> 的 <STRONG>ExecuteOptionEnum</STRONG> 值不起作用。提取和阻止将同步进行。</span><span class="sxs-lookup"><span data-stu-id="96dfa-126">If you open a <STRONG>Recordset</STRONG> from a <STRONG>Stream</STRONG> containing a persisted <STRONG>Recordset</STRONG>, using an <STRONG>ExecuteOptionEnum</STRONG> value of <STRONG>adAsyncFetchNonBlocking</STRONG> will not have an effect; the fetch will be synchronous and blocking.</span></span></P>



<span data-ttu-id="96dfa-127">**adExecuteNoRecords** 或 **adExecuteStream** 的 **ExecuteOpenEnum** 值不应与 **Open** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="96dfa-127">The **ExecuteOpenEnum** values of **adExecuteNoRecords** or **adExecuteStream** should not be used with **Open**.</span></span>

## <a name="remarks"></a><span data-ttu-id="96dfa-128">备注</span><span class="sxs-lookup"><span data-stu-id="96dfa-128">Remarks</span></span>

<span data-ttu-id="96dfa-129">ADO **Recordset** 的默认游标是仅向前型只读游标，位于服务器上。</span><span class="sxs-lookup"><span data-stu-id="96dfa-129">The default cursor for an ADO **Recordset** is a forward-only, read-only cursor located on the server.</span></span>

<span data-ttu-id="96dfa-130">如果对 **Recordset** 对象使用 **Open** 方法，则会打开一个游标，该游标表示来自基表、查询结果或以前保存的 **Recordset** 的记录。</span><span class="sxs-lookup"><span data-stu-id="96dfa-130">Using the **Open** method on a **Recordset** object opens a cursor that represents records from a base table, the results of a query, or a previously saved **Recordset**.</span></span>

<span data-ttu-id="96dfa-131">使用可选的*源*参数指定数据源使用下列选项之一：**命令**对象变量、 SQL 语句、 存储的过程、 表名称、 URL 或完整文件路径名称。</span><span class="sxs-lookup"><span data-stu-id="96dfa-131">Use the optional *Source* argument to specify a data source using one of the following: a **Command** object variable, an SQL statement, a stored procedure, a table name, a URL, or a complete file path name.</span></span> <span data-ttu-id="96dfa-132">如果*源*是文件路径名称，它可以是完整路径 ("c:\\dir\\file.rst")，相对路径 ("...\\file.rst")，或者是 URL ("https://files/file.rst")。</span><span class="sxs-lookup"><span data-stu-id="96dfa-132">If *Source* is a file path name, it can be a full path ("c:\\dir\\file.rst"), a relative path ("..\\file.rst"), or a URL ("https://files/file.rst").</span></span>

<span data-ttu-id="96dfa-133">不建议使用**Open**方法的*Source*参数执行的操作查询，因为没有任何轻松确定呼叫是否成功，则不返回记录。</span><span class="sxs-lookup"><span data-stu-id="96dfa-133">It is not a good idea to use the *Source* argument of the **Open** method to perform an action query that doesnt return records because there is no easy way to determine whether the call succeeded.</span></span> <span data-ttu-id="96dfa-134">这种查询返回的 **Recordset** 将被关闭。</span><span class="sxs-lookup"><span data-stu-id="96dfa-134">The **Recordset** returned by such a query will be closed.</span></span> <span data-ttu-id="96dfa-135">可以改为调用 [Command](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 对象的 **Execute** 方法或 [Connection](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 对象的 **Execute** 方法来执行不返回记录的查询（如 SQL INSERT 语句）。</span><span class="sxs-lookup"><span data-stu-id="96dfa-135">Call the [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) method of a **Command** object or the [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) method of a **Connection** object instead to perform a query that, such as a SQL INSERT statement, that doesnt return records.</span></span>

<span data-ttu-id="96dfa-136">*ActiveConnection*参数对应于[ActiveConnection](activeconnection-property-ado.md)属性，并指定在哪个连接来打开**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="96dfa-136">The *ActiveConnection* argument corresponds to the [ActiveConnection](activeconnection-property-ado.md) property and specifies in which connection to open the **Recordset** object.</span></span> <span data-ttu-id="96dfa-137">如果传递此参数的连接定义，ADO 将使用指定的参数打开新连接。</span><span class="sxs-lookup"><span data-stu-id="96dfa-137">If you pass a connection definition for this argument, ADO opens a new connection using the specified parameters.</span></span> <span data-ttu-id="96dfa-138">与客户端游标打开**Recordset**后 (**CursorLocation** = **adUseClient**)，您可以更改此属性以将更新发送到其他提供程序的值。</span><span class="sxs-lookup"><span data-stu-id="96dfa-138">After opening the **Recordset** with a client-side cursor (**CursorLocation** = **adUseClient**), you can change the value of this property to send updates to another provider.</span></span> <span data-ttu-id="96dfa-139">也可以将此属性设置为 **Nothing** （在 Microsoft Visual Basic 中）或 NULL，以使 **Recordset** 与任何提供程序断开连接。</span><span class="sxs-lookup"><span data-stu-id="96dfa-139">Or you can set this property to **Nothing** (in Microsoft Visual Basic) or NULL to disconnect the **Recordset** from any provider.</span></span> <span data-ttu-id="96dfa-140">但是，更改服务器端游标的 **ActiveConnection** 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="96dfa-140">Changing **ActiveConnection** for a server-side cursor generates an error, however.</span></span>

<span data-ttu-id="96dfa-141">对于直接对应于 **Recordset** 对象属性（*Source*、*CursorType* 和 *LockType*）的其他参数，参数与属性的关系如下所示：</span><span class="sxs-lookup"><span data-stu-id="96dfa-141">For the other arguments that correspond directly to properties of a **Recordset** object (*Source*, *CursorType*, and *LockType*), the relationship of the arguments to the properties is as follows:</span></span>

  - <span data-ttu-id="96dfa-142">打开 **Recordset** 对象之前，属性处于读/写状态。</span><span class="sxs-lookup"><span data-stu-id="96dfa-142">The property is read/write before the **Recordset** object is opened.</span></span>

  - <span data-ttu-id="96dfa-p109">除非执行 **Open** 方法时传递相应的参数，否则不使用属性设置。如果传递参数，则它会替代相应的属性设置，并用参数值更新该属性设置。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p109">The property settings are used unless you pass the corresponding arguments when executing the **Open** method. If you pass an argument, it overrides the corresponding property setting, and the property setting is updated with the argument value.</span></span>

  - <span data-ttu-id="96dfa-145">打开 **Recordset** 对象之后，这些属性变为只读。</span><span class="sxs-lookup"><span data-stu-id="96dfa-145">After you open the **Recordset** object, these properties become read-only.</span></span>


> [!NOTE]
> <P><span data-ttu-id="96dfa-146">[!注释] <STRONG>ActiveConnection</STRONG> 属性仅对于 <STRONG>Source</STRONG> 属性被设置为有效 <A href="source-property-ado-recordset.md">Command</A> 对象的那些 <STRONG>Recordset</STRONG> 对象为只读，即使 <STRONG>Recordset</STRONG> 对象未打开也是如此。</span><span class="sxs-lookup"><span data-stu-id="96dfa-146">The <STRONG>ActiveConnection</STRONG> property is read only for <STRONG>Recordset</STRONG> objects whose <A href="source-property-ado-recordset.md">Source</A> property is set to a valid <STRONG>Command</STRONG> object, even if the <STRONG>Recordset</STRONG> object isn't open.</span></span></P>



<span data-ttu-id="96dfa-147">如果*源*参数中传递的**Command**对象，并且还传递*ActiveConnection*参数，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="96dfa-147">If you pass a **Command** object in the *Source* argument and also pass an *ActiveConnection* argument, an error occurs.</span></span> <span data-ttu-id="96dfa-148">**Command** 对象的 **ActiveConnection** 属性必须事先已设置为有效的 **Connection** 对象或连接字符串。</span><span class="sxs-lookup"><span data-stu-id="96dfa-148">The **ActiveConnection** property of the **Command** object must already be set to a valid **Connection** object or connection string.</span></span>

<span data-ttu-id="96dfa-149">如果*源*参数中传递的**Command**对象以外的内容，可以使用*Options*参数来优化评估*源*参数。</span><span class="sxs-lookup"><span data-stu-id="96dfa-149">If you pass something other than a **Command** object in the *Source* argument, you can use the *Options* argument to optimize evaluation of the *Source* argument.</span></span> <span data-ttu-id="96dfa-150">如果未定义*Options*参数，您可能会遇到降低的性能，因为 ADO 必须进行到提供程序的调用，以确定是否的 SQL 语句、 存储的过程、 URL 或表名称参数。</span><span class="sxs-lookup"><span data-stu-id="96dfa-150">If the *Options* argument is not defined, you may experience diminished performance because ADO must make calls to the provider to determine if the argument is an SQL statement, a stored procedure, a URL, or a table name.</span></span> <span data-ttu-id="96dfa-151">如果您知道哪些*源*类型您使用的，设置在*Options*参数指示 ADO 直接跳转到了相关代码。</span><span class="sxs-lookup"><span data-stu-id="96dfa-151">If you know what *Source* type you're using, setting the *Options* argument instructs ADO to jump directly to the relevant code.</span></span> <span data-ttu-id="96dfa-152">如果在*Options*参数与*源*类型不匹配，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="96dfa-152">If the *Options* argument does not match the *Source* type, an error occurs.</span></span>

<span data-ttu-id="96dfa-153">如果*源*参数中传递**Stream**对象，您不应将信息传递到其他参数。</span><span class="sxs-lookup"><span data-stu-id="96dfa-153">If you pass a **Stream** object in the *Source* argument, you should not pass information into the other arguments.</span></span> <span data-ttu-id="96dfa-154">这样将生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="96dfa-154">Doing so will generate an error.</span></span> <span data-ttu-id="96dfa-155">从**流**中打开**Recordset**时，不会保留**ActiveConnection**信息。</span><span class="sxs-lookup"><span data-stu-id="96dfa-155">The **ActiveConnection** information is not retained when a **Recordset** is opened from a **Stream**.</span></span>

<span data-ttu-id="96dfa-156">*Options*参数的默认值是**adCmdFile** ，如果没有连接与**记录集**相关联。</span><span class="sxs-lookup"><span data-stu-id="96dfa-156">The default for the *Options* argument is **adCmdFile** if no connection is associated with the **Recordset**.</span></span> <span data-ttu-id="96dfa-157">永久存储的 **Recordset** 对象通常属于这种情况。</span><span class="sxs-lookup"><span data-stu-id="96dfa-157">This will typically be the case for persistently stored **Recordset** objects.</span></span>

<span data-ttu-id="96dfa-p114">如果数据源不返回任何记录，则提供程序同时将 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性设置为 **True** ，且不定义当前记录的位置。如果游标类型允许，仍可以在此空 **Recordset** 对象中添加新数据。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p114">If the data source returns no records, the provider sets both the [BOF](bof-eof-properties-ado.md) and [EOF](bof-eof-properties-ado.md) properties to **True**, and the current record position is undefined. You can still add new data to this empty **Recordset** object if the cursor type allows it.</span></span>

<span data-ttu-id="96dfa-p115">结束对打开的 **Recordset** 对象的操作时，请使用 [Close](close-method-ado.md) 方法释放所有关联的系统资源。关闭对象不会将其从内存中删除，您可以更改其属性设置，以后使用 **Open** 方法重新打开对象。若要将对象从内存中彻底删除，请将对象变量设置为 *Nothing*。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p115">When you have concluded your operations over an open **Recordset** object, use the [Close](close-method-ado.md) method to free any associated system resources. Closing an object does not remove it from memory; you can change its property settings and use the **Open** method to open it again later. To completely eliminate an object from memory, set the object variable to *Nothing*.</span></span>

<span data-ttu-id="96dfa-163">在设置**ActiveConnection**属性之前，则调用**Open**没有操作数以创建通过向**Recordset** [Fields](fields-collection-ado.md)集合追加字段创建的**Recordset**的实例。</span><span class="sxs-lookup"><span data-stu-id="96dfa-163">Before the **ActiveConnection** property is set, call **Open** with no operands to create an instance of a **Recordset** created by appending fields to the **Recordset** [Fields](fields-collection-ado.md) collection.</span></span>

<span data-ttu-id="96dfa-164">如果已将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** ，则可以使用以下两种方法之一以异步方式检索行。</span><span class="sxs-lookup"><span data-stu-id="96dfa-164">If you have set the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient**, you can retrieve rows asynchronously in one of two ways.</span></span> <span data-ttu-id="96dfa-165">推荐的方法是将*选项*设置为**adAsyncFetch**。</span><span class="sxs-lookup"><span data-stu-id="96dfa-165">The recommended method is to set *Options* to **adAsyncFetch**.</span></span> <span data-ttu-id="96dfa-166">另外，也可以使用 [Properties](properties-collection-ado.md) 集合中的"Asynchronous Rowset Processing"动态属性，但如果不将 **Options** 参数设置为 **adAsyncFetch** ，相关的检索事件就有可能丢失。</span><span class="sxs-lookup"><span data-stu-id="96dfa-166">Alternatively, you can use the "Asynchronous Rowset Processing" dynamic property in the [Properties](properties-collection-ado.md) collection, but related retrieved events can be lost if you do not set the **Options** parameter to **adAsyncFetch**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="96dfa-167">MS 远程提供程序中的后台提取功能仅支持通过<STRONG>Open</STRONG>方法的<EM>Options</EM>参数。</span><span class="sxs-lookup"><span data-stu-id="96dfa-167">Background fetching in the MS Remote provider is supported only through the <STRONG>Open</STRONG> method's <EM>Options</EM> parameter.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="96dfa-p117">[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</span><span class="sxs-lookup"><span data-stu-id="96dfa-p117">URLs using the http scheme will automatically invoke the <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. For more information, see <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</span></span></P>

