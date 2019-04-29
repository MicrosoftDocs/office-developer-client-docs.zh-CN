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
ms.openlocfilehash: d6a13799da4ef9315f9c23317fa18853d71c72f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420113"
---
# <a name="imapitable--iunknown"></a><span data-ttu-id="c01e1-103">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c01e1-103">IMAPITable : IUnknown</span></span>

  
  
<span data-ttu-id="c01e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c01e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c01e1-105">提供表的只读视图。</span><span class="sxs-lookup"><span data-stu-id="c01e1-105">Provides a read-only view of a table.</span></span> <span data-ttu-id="c01e1-106">客户端和服务提供程序使用**IMAPITable**来操作表的显示方式。</span><span class="sxs-lookup"><span data-stu-id="c01e1-106">**IMAPITable** is used by clients and service providers to manipulate the way a table appears.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c01e1-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c01e1-107">Header file:</span></span>  <br/> |<span data-ttu-id="c01e1-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c01e1-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c01e1-109">公开者:</span><span class="sxs-lookup"><span data-stu-id="c01e1-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="c01e1-110">Table 对象</span><span class="sxs-lookup"><span data-stu-id="c01e1-110">Table objects</span></span>  <br/> |
|<span data-ttu-id="c01e1-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="c01e1-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="c01e1-112">服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="c01e1-112">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="c01e1-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="c01e1-113">Called by:</span></span>  <br/> |<span data-ttu-id="c01e1-114">客户端应用程序、服务提供商</span><span class="sxs-lookup"><span data-stu-id="c01e1-114">Client applications, service providers</span></span>  <br/> |
|<span data-ttu-id="c01e1-115">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="c01e1-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c01e1-116">IID_IMAPITable</span><span class="sxs-lookup"><span data-stu-id="c01e1-116">IID_IMAPITable</span></span>  <br/> |
|<span data-ttu-id="c01e1-117">指针类型:</span><span class="sxs-lookup"><span data-stu-id="c01e1-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="c01e1-118">LPMAPITABLE</span><span class="sxs-lookup"><span data-stu-id="c01e1-118">LPMAPITABLE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c01e1-119">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="c01e1-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="c01e1-120">GetLastError</span><span class="sxs-lookup"><span data-stu-id="c01e1-120">GetLastError</span></span>](imapitable-getlasterror.md) <br/> |<span data-ttu-id="c01e1-121">返回一个[MAPIERROR](mapierror.md)结构, 其中包含有关表格上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="c01e1-121">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error on the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-122">她们</span><span class="sxs-lookup"><span data-stu-id="c01e1-122">Advise</span></span>](imapitable-advise.md) <br/> |<span data-ttu-id="c01e1-123">注册以接收影响表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="c01e1-123">Registers to receive notification of specified events affecting the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-124">Unadvise</span><span class="sxs-lookup"><span data-stu-id="c01e1-124">Unadvise</span></span>](imapitable-unadvise.md) <br/> |<span data-ttu-id="c01e1-125">取消之前为对**IMAPITable:: Advise**方法的调用而设置的通知发送。</span><span class="sxs-lookup"><span data-stu-id="c01e1-125">Cancels the sending of notifications previously set up with a call to the **IMAPITable::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-126">GetStatus</span><span class="sxs-lookup"><span data-stu-id="c01e1-126">GetStatus</span></span>](imapitable-getstatus.md) <br/> |<span data-ttu-id="c01e1-127">返回表的状态和类型。</span><span class="sxs-lookup"><span data-stu-id="c01e1-127">Returns the table's status and type.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-128">SetColumns</span><span class="sxs-lookup"><span data-stu-id="c01e1-128">SetColumns</span></span>](imapitable-setcolumns.md) <br/> |<span data-ttu-id="c01e1-129">定义在表中显示为列的特定属性和属性的顺序。</span><span class="sxs-lookup"><span data-stu-id="c01e1-129">Defines the particular properties and order of properties to appear as columns in the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-130">QueryColumns</span><span class="sxs-lookup"><span data-stu-id="c01e1-130">QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |<span data-ttu-id="c01e1-131">返回表的列的列表。</span><span class="sxs-lookup"><span data-stu-id="c01e1-131">Returns a list of columns for the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-132">GetRowCount</span><span class="sxs-lookup"><span data-stu-id="c01e1-132">GetRowCount</span></span>](imapitable-getrowcount.md) <br/> |<span data-ttu-id="c01e1-133">返回表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="c01e1-133">Returns the total number of rows in the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-134">SeekRow</span><span class="sxs-lookup"><span data-stu-id="c01e1-134">SeekRow</span></span>](imapitable-seekrow.md) <br/> |<span data-ttu-id="c01e1-135">将光标移到表中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="c01e1-135">Moves the cursor to a specific position in the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-136">SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="c01e1-136">SeekRowApprox</span></span>](imapitable-seekrowapprox.md) <br/> |<span data-ttu-id="c01e1-137">将光标移到表中的近似小数位置。</span><span class="sxs-lookup"><span data-stu-id="c01e1-137">Moves the cursor to an approximate fractional position in the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-138">QueryPosition</span><span class="sxs-lookup"><span data-stu-id="c01e1-138">QueryPosition</span></span>](imapitable-queryposition.md) <br/> |<span data-ttu-id="c01e1-139">根据分数值检索游标的当前表行位置。</span><span class="sxs-lookup"><span data-stu-id="c01e1-139">Retrieves the current table row position of the cursor, based on a fractional value.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-140">FindRow</span><span class="sxs-lookup"><span data-stu-id="c01e1-140">FindRow</span></span>](imapitable-findrow.md) <br/> |<span data-ttu-id="c01e1-141">在表中查找与特定搜索条件相匹配的下一行。</span><span class="sxs-lookup"><span data-stu-id="c01e1-141">Finds the next row in a table that matches specific search criteria.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-142">Restrict</span><span class="sxs-lookup"><span data-stu-id="c01e1-142">Restrict</span></span>](imapitable-restrict.md) <br/> |<span data-ttu-id="c01e1-143">将筛选器应用于表, 将行设置为仅将行设置为与指定条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="c01e1-143">Applies a filter to a table, reducing the row set to only those rows matching the specified criteria.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-144">CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="c01e1-144">CreateBookmark</span></span>](imapitable-createbookmark.md) <br/> |<span data-ttu-id="c01e1-145">标记表的当前位置。</span><span class="sxs-lookup"><span data-stu-id="c01e1-145">Marks the table's current position.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-146">FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="c01e1-146">FreeBookmark</span></span>](imapitable-freebookmark.md) <br/> |<span data-ttu-id="c01e1-147">释放与书签关联的内存。</span><span class="sxs-lookup"><span data-stu-id="c01e1-147">Releases the memory associated with a bookmark.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-148">SortTable</span><span class="sxs-lookup"><span data-stu-id="c01e1-148">SortTable</span></span>](imapitable-sorttable.md) <br/> |<span data-ttu-id="c01e1-149">根据排序条件对表中的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="c01e1-149">Orders the rows of the table based on sort criteria.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-150">QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="c01e1-150">QuerySortOrder</span></span>](imapitable-querysortorder.md) <br/> |<span data-ttu-id="c01e1-151">检索表的当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="c01e1-151">Retrieves the current sort order for a table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-152">QueryRows</span><span class="sxs-lookup"><span data-stu-id="c01e1-152">QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="c01e1-153">从当前游标位置开始, 返回表中的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="c01e1-153">Returns one or more rows from a table, beginning at the current cursor position.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-154">中止</span><span class="sxs-lookup"><span data-stu-id="c01e1-154">Abort</span></span>](imapitable-abort.md) <br/> |<span data-ttu-id="c01e1-155">停止当前对表进行的所有异步操作。</span><span class="sxs-lookup"><span data-stu-id="c01e1-155">Stops any asynchronous operations currently in progress for the table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-156">ExpandRow</span><span class="sxs-lookup"><span data-stu-id="c01e1-156">ExpandRow</span></span>](imapitable-expandrow.md) <br/> |<span data-ttu-id="c01e1-157">展开折叠的表类别, 将属于该类别的叶行添加到表视图中。</span><span class="sxs-lookup"><span data-stu-id="c01e1-157">Expands a collapsed table category, adding the leaf rows belonging to the category to the table view.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-158">CollapseRow</span><span class="sxs-lookup"><span data-stu-id="c01e1-158">CollapseRow</span></span>](imapitable-collapserow.md) <br/> |<span data-ttu-id="c01e1-159">折叠展开的表类别, 从表视图中删除属于该类别的叶行。</span><span class="sxs-lookup"><span data-stu-id="c01e1-159">Collapses an expanded table category, removing the leaf rows belonging to the category from the table view.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-160">WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="c01e1-160">WaitForCompletion</span></span>](imapitable-waitforcompletion.md) <br/> |<span data-ttu-id="c01e1-161">在对表进行的一个或多个异步操作完成之前, 挂起处理。</span><span class="sxs-lookup"><span data-stu-id="c01e1-161">Suspends processing until one or more asynchronous operations in progress on the table have completed.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-162">GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="c01e1-162">GetCollapseState</span></span>](imapitable-getcollapsestate.md) <br/> |<span data-ttu-id="c01e1-163">返回重建已分类表的当前折叠或展开状态所需的数据。</span><span class="sxs-lookup"><span data-stu-id="c01e1-163">Returns the data necessary to rebuild the current collapsed or expanded state of a categorized table.</span></span>  <br/> |
|[<span data-ttu-id="c01e1-164">SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="c01e1-164">SetCollapseState</span></span>](imapitable-setcollapsestate.md) <br/> |<span data-ttu-id="c01e1-165">使用以前对**IMAPITable:: GetCollapseState**方法所保存的数据, 重新生成已分类表的当前展开或折叠状态。</span><span class="sxs-lookup"><span data-stu-id="c01e1-165">Rebuilds the current expanded or collapsed state of a categorized table using data that was saved by a prior call to the **IMAPITable::GetCollapseState** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c01e1-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c01e1-166">See also</span></span>



[<span data-ttu-id="c01e1-167">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c01e1-167">MAPI Interfaces</span></span>](mapi-interfaces.md)

