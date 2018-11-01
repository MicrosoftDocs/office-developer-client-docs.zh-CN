---
title: Save 方法的 ActiveX 数据对象 (ADO)
TOCTitle: Save Method (ADO)
ms:assetid: 02dab13b-f947-b96d-46ea-0def3ed8f28f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248793(v=office.15)
ms:contentKeyID: 48542968
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1b4e3698043c109a8f0fbf32c5c2b8c8ae20e824
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875979"
---
# <a name="save-method-ado"></a><span data-ttu-id="62ff3-102">Save 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="62ff3-102">Save Method (ADO)</span></span>


<span data-ttu-id="62ff3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="62ff3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="62ff3-104">可将 [Recordset](recordset-object-ado.md) 保存到文件或 [Stream](stream-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="62ff3-104">Saves the [Recordset](recordset-object-ado.md) in a file or [Stream](stream-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="62ff3-105">语法</span><span class="sxs-lookup"><span data-stu-id="62ff3-105">Syntax</span></span>

<span data-ttu-id="62ff3-106">*记录集*。保存*目标*， *PersistFormat*</span><span class="sxs-lookup"><span data-stu-id="62ff3-106">*recordset*.Save*Destination*, *PersistFormat*</span></span>

## <a name="parameters"></a><span data-ttu-id="62ff3-107">参数</span><span class="sxs-lookup"><span data-stu-id="62ff3-107">Parameters</span></span>

  - <span data-ttu-id="62ff3-108">*Destination*</span><span class="sxs-lookup"><span data-stu-id="62ff3-108">*Destination*</span></span>

  - <span data-ttu-id="62ff3-p101">可选。一个 **变量型** ，表示要保存 **Recordset** 的文件的完整路径名；或 **Stream** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p101">Optional. A **Variant** that represents the complete path name of the file where the **Recordset** is to be saved, or a reference to a **Stream** object.</span></span>

  - <span data-ttu-id="62ff3-111">*PersistFormat*</span><span class="sxs-lookup"><span data-stu-id="62ff3-111">*PersistFormat*</span></span>

  - <span data-ttu-id="62ff3-p102">可选。[PersistFormatEnum](persistformatenum.md) 值，用于指定 **Recordset** 的保存格式（XML 或 ADTG）。默认值为 **adPersistADTG** 。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p102">Optional. A [PersistFormatEnum](persistformatenum.md) value that specifies the format in which the **Recordset** is to be saved (XML or ADTG). The default value is **adPersistADTG**.</span></span>

## <a name="remarks"></a><span data-ttu-id="62ff3-115">备注</span><span class="sxs-lookup"><span data-stu-id="62ff3-115">Remarks</span></span>

<span data-ttu-id="62ff3-p103">只能对打开的 **Recordset** 调用 **Save** 方法。使用 [Open](open-method-ado-recordset.md) 方法以便以后从 *Destination* 中还原 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p103">The **Save** method can only be invoked on an open **Recordset**. Use the [Open](open-method-ado-recordset.md) method to later restore the **Recordset** from *Destination*.</span></span>

<span data-ttu-id="62ff3-p104">如果 [Filter](filter-property-ado.md) 属性对于 **Recordset** 有效，则只保存可通过筛选访问的行。如果 **Recordset** 是分层结构，则保存当前子 **Recordset** 及其子级，包括父 **Recordset** 。如果调用子 **Recordset** 的 **Save** 方法，则保存该子记录集及其所有子记录集，但不保存父记录集。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p104">If the [Filter](filter-property-ado.md) property is in effect for the **Recordset**, then only the rows accessible under the filter are saved. If the **Recordset** is hierarchical, then the current child **Recordset** and its children are saved, including the parent **Recordset**. If the **Save** method of a child **Recordset** is called, the child and all its children are saved, but the parent is not.</span></span>

<span data-ttu-id="62ff3-p105">第一次保存 **Recordset** 时，可以选择指定 *Destination*。如果省略 *Destination*，系统将创建新文件，文件名为 **Recordset** 的 [Source](source-property-ado-recordset.md) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p105">The first time you save the **Recordset**, it is optional to specify *Destination*. If you omit *Destination*, a new file will be created with a name set to the value of the [Source](source-property-ado-recordset.md) property of the **Recordset**.</span></span>

<span data-ttu-id="62ff3-123">您随后调用**保存**后第一个保存，或将发生运行时错误时，请省略*目标*。</span><span class="sxs-lookup"><span data-stu-id="62ff3-123">Omit *Destination* when you subsequently call **Save** after the first save, or a run-time error will occur.</span></span> <span data-ttu-id="62ff3-124">如果您随后调用**保存**新的*目标*， **Recordset**保存到新的目标位置。</span><span class="sxs-lookup"><span data-stu-id="62ff3-124">If you subsequently call **Save** with a new *Destination*, the **Recordset** is saved to the new destination.</span></span> <span data-ttu-id="62ff3-125">但是，新的目标和原始目标都将打开。</span><span class="sxs-lookup"><span data-stu-id="62ff3-125">However, the new destination and the original destination will both be open.</span></span>

<span data-ttu-id="62ff3-p107">**Save** 不会关闭 **Recordset** 或 *Destination*，因此可以继续使用 **Recordset** 并保存最新的更改。在关闭 **Recordset** 之前，*Destination* 一直是打开的。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p107">**Save** does not close the **Recordset** or *Destination*, so you can continue to work with the **Recordset** and save your most recent changes. *Destination* remains open until the **Recordset** is closed.</span></span>

<span data-ttu-id="62ff3-p108">由于安全原因， **Save** 方法只允许在 Microsoft Internet Explorer 执行的脚本中使用低安全设置和自定义安全设置。有关安全问题的详细说明，请参阅 Microsoft 数据访问技术文章中 ActiveX 数据对象 (ADO) 技术文章下的"ADO and RDS Security Issues in Microsoft Internet Explorer"（Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题）。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p108">For reasons of security, the **Save** method permits only the use of low and custom security settings from a script executed by Microsoft Internet Explorer. For a more detailed explanation of security issues, see "ADO and RDS Security Issues in Microsoft Internet Explorer" under ActiveX Data Objects (ADO) Technical Articles in Microsoft Data Access Technical Articles.</span></span>

<span data-ttu-id="62ff3-130">如果在执行异步 **Recordset** 提取、执行或更新操作时调用 **Save** 方法，则将等到异步操作完成后，才执行 **Save** 。</span><span class="sxs-lookup"><span data-stu-id="62ff3-130">If the **Save** method is called while an asynchronous **Recordset** fetch, execute, or update operation is in progress, then **Save** waits until the asynchronous operation is complete.</span></span>

<span data-ttu-id="62ff3-p109">记录的保存是从 **Recordset** 的第一行开始的。 **Save** 方法完成之后，当前行位置被移到 **Recordset** 的第一行。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p109">Records are saved beginning with the first row of the **Recordset**. When the **Save** method is finished, the current row position is moved to the first row of the **Recordset**.</span></span>

<span data-ttu-id="62ff3-p110">为获得最佳结果，请用 [Save](cursorlocation-property-ado.md) 方法将 **CursorLocation** 属性设置为 **adUseClient** 。如果提供程序不支持保存 **Recordset** 对象所需的所有功能，则游标服务将提供该功能。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p110">For best results, set the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient** with **Save**. If your provider does not support all of the functionality necessary to save **Recordset** objects, the Cursor Service will provide that functionality.</span></span>

<span data-ttu-id="62ff3-p111">如果在持久化 **Recordset** 时将 **CursorLocation** 属性设置为 **adUseServer** ，则 **Recordset** 的更新功能会受到限制。通常，只允许对单个表进行更新、插入和删除操作（具体取决于提供程序功能）。在此配置中， [Resync](resync-method-ado.md) 方法也不可用。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p111">When a **Recordset** is persisted with the **CursorLocation** property set to **adUseServer**, the update capability for the **Recordset** is limited. Typically, only single-table updates, insertions, and deletions are allowed (dependant upon provider functionality). The [Resync](resync-method-ado.md) method is also unavailable in this configuration.</span></span>


> [!NOTE]
> <P><span data-ttu-id="62ff3-138">[!注释] ADO 不支持保存含有 <STRONG>adVariant</STRONG> 、 <STRONG>adIDispatch</STRONG> 或 <STRONG>adIUnknown</STRONG> 类型 <STRONG>Fields</STRONG> 的 <STRONG>Recordset</STRONG> ，这样做可能会导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="62ff3-138">Saving a <STRONG>Recordset</STRONG> with <STRONG>Fields</STRONG> of type <STRONG>adVariant</STRONG>, <STRONG>adIDispatch</STRONG>, or <STRONG>adIUnknown</STRONG> is not supported by ADO and can cause unpredictable results.</span></span></P>



<span data-ttu-id="62ff3-139">仅**筛选器**条件字符串的形式 (如订购日期\>"12/31/1999年 ') 影响**Recordset**的内容。</span><span class="sxs-lookup"><span data-stu-id="62ff3-139">Only **Filters** in the form of Criteria Strings (e.g. OrderDate \> '12/31/1999') affect the contents of a persisted **Recordset**.</span></span> <span data-ttu-id="62ff3-140">通过 **Bookmark** 数组或使用 **FilterGroupEnum** 中的值创建的 **Filter** 不会影响持久 Recordset 的内容。</span><span class="sxs-lookup"><span data-stu-id="62ff3-140">Filters created with an Array of **Bookmarks** or using a value from the **FilterGroupEnum** will not affect the contents of the persisted **Recordset**.</span></span> <span data-ttu-id="62ff3-141">这些规则适用于通过客户端或服务器端游标创建的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="62ff3-141">These rules apply to **Recordsets** created with either client-side or server-side cursors.</span></span>

<span data-ttu-id="62ff3-142">由于*Destination*参数可以接受支持 OLE DB IStream 接口的任何对象，可以将**Recordset**保存到 ASP Response 对象直接。</span><span class="sxs-lookup"><span data-stu-id="62ff3-142">Because the *Destination* parameter can accept any object that supports the OLE DB IStream interface, you can save a **Recordset** directly to the ASP Response object.</span></span> <span data-ttu-id="62ff3-143">有关详细信息，请参阅 [XML Recordset 持久化方案](xml-recordset-persistence-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="62ff3-143">For more details, please see the [XML Recordset Persistence Scenario](xml-recordset-persistence-scenario.md).</span></span>

<span data-ttu-id="62ff3-144">此外，还可以将 **Recordset** 以 XML 格式保存到 MSXML DOM 对象的实例，如以下 Visual Basic 代码所示：</span><span class="sxs-lookup"><span data-stu-id="62ff3-144">You can also save a **Recordset** in XML format to an instance of an MSXML DOM object, as is shown in the following Visual Basic code:</span></span>


> [!NOTE]
> <P><span data-ttu-id="62ff3-p114">[!注释] 在以 XML 格式保存分层 <STRONG>Recordsets</STRONG> （数据形状）时有两个限制。其一，如果分层 <STRONG>Recordset</STRONG> 中包含挂起更新，则不能保存到 XML。其二，不能保存参数化的分层 <STRONG>Recordset</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p114">Two limitations apply when saving hierarchical <STRONG>Recordsets</STRONG> (data shapes) in XML format. You cannot save into XML if the hierarchical <STRONG>Recordset</STRONG> contains pending updates, and you cannot save a parameterized hierarchical <STRONG>Recordset</STRONG>.</span></span></P>



<span data-ttu-id="62ff3-p115">以 XML 格式保存的 Recordset 采用 UTF-8 格式保存。当此类文件加载到 ADO 流时，Stream 对象不会尝试从流打开 Recordset，除非流的 Charset 属性设置为正确的 UTF-8 值。</span><span class="sxs-lookup"><span data-stu-id="62ff3-p115">A Recordset saved in XML format is saved using UTF-8 format. When such a file is loaded into an ADO Stream, the Stream object will not attempt to open a Recordset from the stream unless the Charset property of the stream is set to the appropriate value for UTF-8 format.</span></span>

