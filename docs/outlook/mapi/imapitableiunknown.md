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
# <a name="imapitable--iunknown"></a><span data-ttu-id="dbc19-103">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dbc19-103">IMAPITable : IUnknown</span></span>

  
  
<span data-ttu-id="dbc19-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dbc19-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dbc19-105">提供表的只读视图。</span><span class="sxs-lookup"><span data-stu-id="dbc19-105">Provides a read-only view of a table.</span></span> <span data-ttu-id="dbc19-106">客户端和服务提供商使用 **IMAPITable** 操作表的显示方式。</span><span class="sxs-lookup"><span data-stu-id="dbc19-106">**IMAPITable** is used by clients and service providers to manipulate the way a table appears.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dbc19-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="dbc19-107">Header file:</span></span>  <br/> |<span data-ttu-id="dbc19-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dbc19-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="dbc19-109">公开者：</span><span class="sxs-lookup"><span data-stu-id="dbc19-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="dbc19-110">Table 对象</span><span class="sxs-lookup"><span data-stu-id="dbc19-110">Table objects</span></span>  <br/> |
|<span data-ttu-id="dbc19-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="dbc19-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="dbc19-112">服务提供程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="dbc19-112">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="dbc19-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="dbc19-113">Called by:</span></span>  <br/> |<span data-ttu-id="dbc19-114">客户端应用程序、服务提供商</span><span class="sxs-lookup"><span data-stu-id="dbc19-114">Client applications, service providers</span></span>  <br/> |
|<span data-ttu-id="dbc19-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="dbc19-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="dbc19-116">IID_IMAPITable</span><span class="sxs-lookup"><span data-stu-id="dbc19-116">IID_IMAPITable</span></span>  <br/> |
|<span data-ttu-id="dbc19-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="dbc19-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="dbc19-118">LPMAPITABLE</span><span class="sxs-lookup"><span data-stu-id="dbc19-118">LPMAPITABLE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="dbc19-119">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="dbc19-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="dbc19-120">GetLastError</span><span class="sxs-lookup"><span data-stu-id="dbc19-120">GetLastError</span></span>](imapitable-getlasterror.md) <br/> |<span data-ttu-id="dbc19-121">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表上上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="dbc19-121">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error on the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-122">建议</span><span class="sxs-lookup"><span data-stu-id="dbc19-122">Advise</span></span>](imapitable-advise.md) <br/> |<span data-ttu-id="dbc19-123">注册以接收影响表的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="dbc19-123">Registers to receive notification of specified events affecting the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-124">非企业</span><span class="sxs-lookup"><span data-stu-id="dbc19-124">Unadvise</span></span>](imapitable-unadvise.md) <br/> |<span data-ttu-id="dbc19-125">取消发送以前通过调用 **IMAPITable：：Advise** 方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="dbc19-125">Cancels the sending of notifications previously set up with a call to the **IMAPITable::Advise** method.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-126">GetStatus</span><span class="sxs-lookup"><span data-stu-id="dbc19-126">GetStatus</span></span>](imapitable-getstatus.md) <br/> |<span data-ttu-id="dbc19-127">返回表的状态和类型。</span><span class="sxs-lookup"><span data-stu-id="dbc19-127">Returns the table's status and type.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-128">SetColumns</span><span class="sxs-lookup"><span data-stu-id="dbc19-128">SetColumns</span></span>](imapitable-setcolumns.md) <br/> |<span data-ttu-id="dbc19-129">定义要作为表格中的列显示的属性的特定属性和顺序。</span><span class="sxs-lookup"><span data-stu-id="dbc19-129">Defines the particular properties and order of properties to appear as columns in the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-130">QueryColumns</span><span class="sxs-lookup"><span data-stu-id="dbc19-130">QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |<span data-ttu-id="dbc19-131">返回表格的列列表。</span><span class="sxs-lookup"><span data-stu-id="dbc19-131">Returns a list of columns for the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-132">GetRowCount</span><span class="sxs-lookup"><span data-stu-id="dbc19-132">GetRowCount</span></span>](imapitable-getrowcount.md) <br/> |<span data-ttu-id="dbc19-133">返回表中的总行数。</span><span class="sxs-lookup"><span data-stu-id="dbc19-133">Returns the total number of rows in the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-134">SeekRow</span><span class="sxs-lookup"><span data-stu-id="dbc19-134">SeekRow</span></span>](imapitable-seekrow.md) <br/> |<span data-ttu-id="dbc19-135">将光标移到表格中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="dbc19-135">Moves the cursor to a specific position in the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-136">SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="dbc19-136">SeekRowApprox</span></span>](imapitable-seekrowapprox.md) <br/> |<span data-ttu-id="dbc19-137">将光标移到表格中的近似小数位置。</span><span class="sxs-lookup"><span data-stu-id="dbc19-137">Moves the cursor to an approximate fractional position in the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-138">QueryPosition</span><span class="sxs-lookup"><span data-stu-id="dbc19-138">QueryPosition</span></span>](imapitable-queryposition.md) <br/> |<span data-ttu-id="dbc19-139">基于小数值检索游标的当前表格行位置。</span><span class="sxs-lookup"><span data-stu-id="dbc19-139">Retrieves the current table row position of the cursor, based on a fractional value.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-140">FindRow</span><span class="sxs-lookup"><span data-stu-id="dbc19-140">FindRow</span></span>](imapitable-findrow.md) <br/> |<span data-ttu-id="dbc19-141">查找表中与特定搜索条件匹配的下一行。</span><span class="sxs-lookup"><span data-stu-id="dbc19-141">Finds the next row in a table that matches specific search criteria.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-142">Restrict</span><span class="sxs-lookup"><span data-stu-id="dbc19-142">Restrict</span></span>](imapitable-restrict.md) <br/> |<span data-ttu-id="dbc19-143">将筛选器应用于表，从而将行设置为仅与指定条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="dbc19-143">Applies a filter to a table, reducing the row set to only those rows matching the specified criteria.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-144">CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="dbc19-144">CreateBookmark</span></span>](imapitable-createbookmark.md) <br/> |<span data-ttu-id="dbc19-145">标记表的当前位置。</span><span class="sxs-lookup"><span data-stu-id="dbc19-145">Marks the table's current position.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-146">FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="dbc19-146">FreeBookmark</span></span>](imapitable-freebookmark.md) <br/> |<span data-ttu-id="dbc19-147">释放与书签关联的内存。</span><span class="sxs-lookup"><span data-stu-id="dbc19-147">Releases the memory associated with a bookmark.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-148">SortTable</span><span class="sxs-lookup"><span data-stu-id="dbc19-148">SortTable</span></span>](imapitable-sorttable.md) <br/> |<span data-ttu-id="dbc19-149">根据排序条件对表的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="dbc19-149">Orders the rows of the table based on sort criteria.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-150">QuerySortOrder</span><span class="sxs-lookup"><span data-stu-id="dbc19-150">QuerySortOrder</span></span>](imapitable-querysortorder.md) <br/> |<span data-ttu-id="dbc19-151">检索表的当前排序顺序。</span><span class="sxs-lookup"><span data-stu-id="dbc19-151">Retrieves the current sort order for a table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-152">QueryRows</span><span class="sxs-lookup"><span data-stu-id="dbc19-152">QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="dbc19-153">从表中的一行或多行，从当前光标位置开始。</span><span class="sxs-lookup"><span data-stu-id="dbc19-153">Returns one or more rows from a table, beginning at the current cursor position.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-154">中止</span><span class="sxs-lookup"><span data-stu-id="dbc19-154">Abort</span></span>](imapitable-abort.md) <br/> |<span data-ttu-id="dbc19-155">停止表当前正在执行的任何异步操作。</span><span class="sxs-lookup"><span data-stu-id="dbc19-155">Stops any asynchronous operations currently in progress for the table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-156">ExpandRow</span><span class="sxs-lookup"><span data-stu-id="dbc19-156">ExpandRow</span></span>](imapitable-expandrow.md) <br/> |<span data-ttu-id="dbc19-157">展开折叠的表类别，将属于该类别的叶行添加到表视图中。</span><span class="sxs-lookup"><span data-stu-id="dbc19-157">Expands a collapsed table category, adding the leaf rows belonging to the category to the table view.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-158">CollapseRow</span><span class="sxs-lookup"><span data-stu-id="dbc19-158">CollapseRow</span></span>](imapitable-collapserow.md) <br/> |<span data-ttu-id="dbc19-159">折叠展开的表类别，从表视图中删除属于该类别的叶行。</span><span class="sxs-lookup"><span data-stu-id="dbc19-159">Collapses an expanded table category, removing the leaf rows belonging to the category from the table view.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-160">WaitForCompletion</span><span class="sxs-lookup"><span data-stu-id="dbc19-160">WaitForCompletion</span></span>](imapitable-waitforcompletion.md) <br/> |<span data-ttu-id="dbc19-161">在表上的一个或多个异步操作完成之前暂停处理。</span><span class="sxs-lookup"><span data-stu-id="dbc19-161">Suspends processing until one or more asynchronous operations in progress on the table have completed.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-162">GetCollapseState</span><span class="sxs-lookup"><span data-stu-id="dbc19-162">GetCollapseState</span></span>](imapitable-getcollapsestate.md) <br/> |<span data-ttu-id="dbc19-163">返回重新生成分类表的当前折叠或展开状态所需的数据。</span><span class="sxs-lookup"><span data-stu-id="dbc19-163">Returns the data necessary to rebuild the current collapsed or expanded state of a categorized table.</span></span>  <br/> |
|[<span data-ttu-id="dbc19-164">SetCollapseState</span><span class="sxs-lookup"><span data-stu-id="dbc19-164">SetCollapseState</span></span>](imapitable-setcollapsestate.md) <br/> |<span data-ttu-id="dbc19-165">使用之前调用 **IMAPITable：：GetCollapseState** 方法保存的数据重新生成分类表的当前展开或折叠状态。</span><span class="sxs-lookup"><span data-stu-id="dbc19-165">Rebuilds the current expanded or collapsed state of a categorized table using data that was saved by a prior call to the **IMAPITable::GetCollapseState** method.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dbc19-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbc19-166">See also</span></span>



[<span data-ttu-id="dbc19-167">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="dbc19-167">MAPI Interfaces</span></span>](mapi-interfaces.md)

