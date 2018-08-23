---
title: IMAPITable IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPITable
api_type:
- COM
ms.assetid: f25be2b1-0f94-4a0c-b29d-d2201dc70ab7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a5504711bdeac4ef94cbe47395ceb8163b60ad68
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584329"
---
# <a name="imapitable--iunknown"></a><span data-ttu-id="3ddd8-103">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3ddd8-103">IMAPITable : IUnknown</span></span>

  
  
<span data-ttu-id="3ddd8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ddd8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3ddd8-105">提供一个表的只读视图。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-105">Provides a read-only view of a table.</span></span> <span data-ttu-id="3ddd8-106">客户端和服务提供商使用**IMAPITable**来操作表的显示的方式。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-106">**IMAPITable** is used by clients and service providers to manipulate the way a table appears.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3ddd8-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="3ddd8-107">Header file:</span></span>  <br/> |<span data-ttu-id="3ddd8-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3ddd8-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="3ddd8-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="3ddd8-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="3ddd8-110">Table 对象</span><span class="sxs-lookup"><span data-stu-id="3ddd8-110">Table objects</span></span>  <br/> |
|<span data-ttu-id="3ddd8-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="3ddd8-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="3ddd8-112">服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="3ddd8-112">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="3ddd8-113">调用：</span><span class="sxs-lookup"><span data-stu-id="3ddd8-113">Called by:</span></span>  <br/> |<span data-ttu-id="3ddd8-114">客户端应用程序，服务提供商</span><span class="sxs-lookup"><span data-stu-id="3ddd8-114">Client applications, service providers</span></span>  <br/> |
|<span data-ttu-id="3ddd8-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="3ddd8-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="3ddd8-116">IID_IMAPITable</span><span class="sxs-lookup"><span data-stu-id="3ddd8-116">IID_IMAPITable</span></span>  <br/> |
|<span data-ttu-id="3ddd8-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="3ddd8-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="3ddd8-118">LPMAPITABLE</span><span class="sxs-lookup"><span data-stu-id="3ddd8-118">LPMAPITABLE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="3ddd8-119">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="3ddd8-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="3ddd8-120">时出错</span><span class="sxs-lookup"><span data-stu-id="3ddd8-120">GetLastError</span></span>](imapitable-getlasterror.md) <br/> |<span data-ttu-id="3ddd8-121">返回[MAPIERROR](mapierror.md)结构包含有关在表格的上一个错误。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-121">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error on the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-122">建议</span><span class="sxs-lookup"><span data-stu-id="3ddd8-122">Advise</span></span>](imapitable-advise.md) <br/> |<span data-ttu-id="3ddd8-123">注册接收影响表指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-123">Registers to receive notification of specified events affecting the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-124">取消通知</span><span class="sxs-lookup"><span data-stu-id="3ddd8-124">Unadvise</span></span>](imapitable-unadvise.md) <br/> |<span data-ttu-id="3ddd8-125">取消发送通知之前设置与对**IMAPITable::Advise**方法的调用。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-125">Cancels the sending of notifications previously set up with a call to the **IMAPITable::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-126">GetStatus</span><span class="sxs-lookup"><span data-stu-id="3ddd8-126">GetStatus</span></span>](imapitable-getstatus.md) <br/> |<span data-ttu-id="3ddd8-127">返回表的状态和类型。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-127">Returns the table's status and type.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-128">SetColumns</span><span class="sxs-lookup"><span data-stu-id="3ddd8-128">SetColumns</span></span>](imapitable-setcolumns.md) <br/> |<span data-ttu-id="3ddd8-129">定义的特定属性和属性的顺序显示为表中的列。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-129">Defines the particular properties and order of properties to appear as columns in the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-130">QueryColumns</span><span class="sxs-lookup"><span data-stu-id="3ddd8-130">QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |<span data-ttu-id="3ddd8-131">返回表格列的列表。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-131">Returns a list of columns for the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-132">GetRowCount</span><span class="sxs-lookup"><span data-stu-id="3ddd8-132">GetRowCount</span></span>](imapitable-getrowcount.md) <br/> |<span data-ttu-id="3ddd8-133">返回表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-133">Returns the total number of rows in the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-134">SeekRow</span><span class="sxs-lookup"><span data-stu-id="3ddd8-134">SeekRow</span></span>](imapitable-seekrow.md) <br/> |<span data-ttu-id="3ddd8-135">将光标移到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-135">Moves the cursor to a specific position in the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-136">SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="3ddd8-136">SeekRowApprox</span></span>](imapitable-seekrowapprox.md) <br/> |<span data-ttu-id="3ddd8-137">将光标移到表中大约小数位置。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-137">Moves the cursor to an approximate fractional position in the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-138">QueryPosition</span><span class="sxs-lookup"><span data-stu-id="3ddd8-138">QueryPosition</span></span>](imapitable-queryposition.md) <br/> |<span data-ttu-id="3ddd8-139">检索当前表行位置的指针，根据分数的值。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-139">Retrieves the current table row position of the cursor, based on a fractional value.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-140">FindRow</span><span class="sxs-lookup"><span data-stu-id="3ddd8-140">FindRow</span></span>](imapitable-findrow.md) <br/> |<span data-ttu-id="3ddd8-141">与特定的搜索条件匹配的表中查找的下一行。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-141">Finds the next row in a table that matches specific search criteria.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-142">限制</span><span class="sxs-lookup"><span data-stu-id="3ddd8-142">Restrict</span></span>](imapitable-restrict.md) <br/> |<span data-ttu-id="3ddd8-143">筛选器应用于表格，从而减少了设置为仅与指定的条件匹配这些行的行。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-143">Applies a filter to a table, reducing the row set to only those rows matching the specified criteria.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-144">CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="3ddd8-144">CreateBookmark</span></span>](imapitable-createbookmark.md) <br/> |<span data-ttu-id="3ddd8-145">标记表的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-145">Marks the table's current position.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-146">FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="3ddd8-146">FreeBookmark</span></span>](imapitable-freebookmark.md) <br/> |<span data-ttu-id="3ddd8-147">释放与一个书签关联的内存。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-147">Releases the memory associated with a bookmark.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-148">SortTable</span><span class="sxs-lookup"><span data-stu-id="3ddd8-148">SortTable</span></span>](imapitable-sorttable.md) <br/> |<span data-ttu-id="3ddd8-149">基于排序条件的表的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-149">Orders the rows of the table based on sort criteria.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-150">QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="3ddd8-150">QuerySortOrder</span></span>](imapitable-querysortorder.md) <br/> |<span data-ttu-id="3ddd8-151">检索当前表格排序顺序。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-151">Retrieves the current sort order for a table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-152">QueryRows</span><span class="sxs-lookup"><span data-stu-id="3ddd8-152">QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="3ddd8-153">从表中，开始在当前光标位置返回一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-153">Returns one or more rows from a table, beginning at the current cursor position.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-154">中止</span><span class="sxs-lookup"><span data-stu-id="3ddd8-154">Abort</span></span>](imapitable-abort.md) <br/> |<span data-ttu-id="3ddd8-155">停止当前正在进行任何异步操作表。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-155">Stops any asynchronous operations currently in progress for the table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-156">ExpandRow</span><span class="sxs-lookup"><span data-stu-id="3ddd8-156">ExpandRow</span></span>](imapitable-expandrow.md) <br/> |<span data-ttu-id="3ddd8-157">展开折叠的表类别，添加属于到表视图类别的叶行。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-157">Expands a collapsed table category, adding the leaf rows belonging to the category to the table view.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-158">CollapseRow</span><span class="sxs-lookup"><span data-stu-id="3ddd8-158">CollapseRow</span></span>](imapitable-collapserow.md) <br/> |<span data-ttu-id="3ddd8-159">折叠的扩展的表类别，删除属于表视图中的类别的叶行。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-159">Collapses an expanded table category, removing the leaf rows belonging to the category from the table view.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-160">WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="3ddd8-160">WaitForCompletion</span></span>](imapitable-waitforcompletion.md) <br/> |<span data-ttu-id="3ddd8-161">挂起处理，直到完成一个或多个异步正在进行的操作在表上。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-161">Suspends processing until one or more asynchronous operations in progress on the table have completed.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-162">GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="3ddd8-162">GetCollapseState</span></span>](imapitable-getcollapsestate.md) <br/> |<span data-ttu-id="3ddd8-163">返回要重新生成当前的必需数据折叠或展开分类表的状态。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-163">Returns the data necessary to rebuild the current collapsed or expanded state of a categorized table.</span></span>  <br/> |
|[<span data-ttu-id="3ddd8-164">SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="3ddd8-164">SetCollapseState</span></span>](imapitable-setcollapsestate.md) <br/> |<span data-ttu-id="3ddd8-165">重建使用以前**IMAPITable::GetCollapseState**方法调用已保存的数据分类表的当前展开还是折叠状态。</span><span class="sxs-lookup"><span data-stu-id="3ddd8-165">Rebuilds the current expanded or collapsed state of a categorized table using data that was saved by a prior call to the **IMAPITable::GetCollapseState** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3ddd8-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ddd8-166">See also</span></span>



[<span data-ttu-id="3ddd8-167">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="3ddd8-167">MAPI Interfaces</span></span>](mapi-interfaces.md)

