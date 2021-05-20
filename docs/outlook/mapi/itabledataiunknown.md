---
title: ITableData IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData
api_type:
- COM
ms.assetid: ac7ae09f-ce19-45cf-8963-fad5bba75452
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3992bea899239ee5975505dec366490d6bbe1698
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430593"
---
# <a name="itabledata--iunknown"></a><span data-ttu-id="a2615-103">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a2615-103">ITableData : IUnknown</span></span>

  
  
<span data-ttu-id="a2615-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2615-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2615-105">提供用于处理表的实用程序方法。</span><span class="sxs-lookup"><span data-stu-id="a2615-105">Provides utility methods for working with tables.</span></span> <span data-ttu-id="a2615-106">MAPI 提供实现 **ITableData** 的表数据对象，以帮助服务提供商执行表维护。</span><span class="sxs-lookup"><span data-stu-id="a2615-106">MAPI provides table data objects or objects that implement **ITableData** to help service providers perform table maintenance.</span></span> <span data-ttu-id="a2615-107">若要获取表数据对象，服务提供商调用 [CreateTable](createtable.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="a2615-107">To obtain a table data object, service providers call the [CreateTable](createtable.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a2615-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a2615-108">Header file:</span></span>  <br/> |<span data-ttu-id="a2615-109">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a2615-109">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a2615-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="a2615-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="a2615-111">表数据对象</span><span class="sxs-lookup"><span data-stu-id="a2615-111">Table data objects</span></span>  <br/> |
|<span data-ttu-id="a2615-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="a2615-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="a2615-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="a2615-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="a2615-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="a2615-114">Called by:</span></span>  <br/> |<span data-ttu-id="a2615-115">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="a2615-115">Service providers</span></span>  <br/> |
|<span data-ttu-id="a2615-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="a2615-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="a2615-117">IID_IMAPITableData</span><span class="sxs-lookup"><span data-stu-id="a2615-117">IID_IMAPITableData</span></span>  <br/> |
|<span data-ttu-id="a2615-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="a2615-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="a2615-119">LPTABLEDATA</span><span class="sxs-lookup"><span data-stu-id="a2615-119">LPTABLEDATA</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="a2615-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="a2615-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="a2615-121">HrGetView</span><span class="sxs-lookup"><span data-stu-id="a2615-121">HrGetView</span></span>](itabledata-hrgetview.md) <br/> |<span data-ttu-id="a2615-122">创建表视图，返回指向 [IMAPITable](imapitableiunknown.md) 实现指针。</span><span class="sxs-lookup"><span data-stu-id="a2615-122">Creates a table view, returning a pointer to an [IMAPITable](imapitableiunknown.md) implementation.</span></span>  <br/> |
|[<span data-ttu-id="a2615-123">HrModifyRow</span><span class="sxs-lookup"><span data-stu-id="a2615-123">HrModifyRow</span></span>](itabledata-hrmodifyrow.md) <br/> |<span data-ttu-id="a2615-124">插入新的表格行，可能会替换现有的行。</span><span class="sxs-lookup"><span data-stu-id="a2615-124">Inserts a new table row, possibly replacing an existing row.</span></span>  <br/> |
|[<span data-ttu-id="a2615-125">HrDeleteRow</span><span class="sxs-lookup"><span data-stu-id="a2615-125">HrDeleteRow</span></span>](itabledata-hrdeleterow.md) <br/> |<span data-ttu-id="a2615-126">删除表格行。</span><span class="sxs-lookup"><span data-stu-id="a2615-126">Deletes a table row.</span></span>  <br/> |
|[<span data-ttu-id="a2615-127">HrQueryRow</span><span class="sxs-lookup"><span data-stu-id="a2615-127">HrQueryRow</span></span>](itabledata-hrqueryrow.md) <br/> |<span data-ttu-id="a2615-128">检索表行。</span><span class="sxs-lookup"><span data-stu-id="a2615-128">Retrieves a table row.</span></span>  <br/> |
|[<span data-ttu-id="a2615-129">HrEnumRow</span><span class="sxs-lookup"><span data-stu-id="a2615-129">HrEnumRow</span></span>](itabledata-hrenumrow.md) <br/> |<span data-ttu-id="a2615-130">根据行在表中的位置检索行。</span><span class="sxs-lookup"><span data-stu-id="a2615-130">Retrieves a row based on its position in the table.</span></span>  <br/> |
|[<span data-ttu-id="a2615-131">HrNotify</span><span class="sxs-lookup"><span data-stu-id="a2615-131">HrNotify</span></span>](itabledata-hrnotify.md) <br/> |<span data-ttu-id="a2615-132">发送表行的通知。</span><span class="sxs-lookup"><span data-stu-id="a2615-132">Sends a notification for a table row.</span></span>  <br/> |
|[<span data-ttu-id="a2615-133">HrInsertRow</span><span class="sxs-lookup"><span data-stu-id="a2615-133">HrInsertRow</span></span>](itabledata-hrinsertrow.md) <br/> |<span data-ttu-id="a2615-134">插入表格行。</span><span class="sxs-lookup"><span data-stu-id="a2615-134">Inserts a table row.</span></span>  <br/> |
|[<span data-ttu-id="a2615-135">HrModifyRows</span><span class="sxs-lookup"><span data-stu-id="a2615-135">HrModifyRows</span></span>](itabledata-hrmodifyrows.md) <br/> |<span data-ttu-id="a2615-136">插入多个表格行，可能会替换现有行。</span><span class="sxs-lookup"><span data-stu-id="a2615-136">Inserts multiple table rows, possibly replacing existing rows.</span></span>  <br/> |
|[<span data-ttu-id="a2615-137">HrDeleteRows</span><span class="sxs-lookup"><span data-stu-id="a2615-137">HrDeleteRows</span></span>](itabledata-hrdeleterows.md) <br/> |<span data-ttu-id="a2615-138">删除多个表格行。</span><span class="sxs-lookup"><span data-stu-id="a2615-138">Deletes multiple table rows.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a2615-139">备注</span><span class="sxs-lookup"><span data-stu-id="a2615-139">Remarks</span></span>

<span data-ttu-id="a2615-140">**ITableData** 的 MAPI 实现通过将所有数据和任何关联限制都存储到内存中来使用表，从而不适合用于非常大的表。</span><span class="sxs-lookup"><span data-stu-id="a2615-140">The MAPI implementation of **ITableData** works with tables by holding all of the data and any associated restrictions in memory, making it unsuitable for use with very large tables.</span></span> <span data-ttu-id="a2615-141">不支持大型限制和复杂操作，如分类。</span><span class="sxs-lookup"><span data-stu-id="a2615-141">Large restrictions and complex operations such as categorization are not supported.</span></span> 
  
<span data-ttu-id="a2615-142">表数据对象通过使用索引列来标识行，索引列是保证每行具有唯一值的属性。</span><span class="sxs-lookup"><span data-stu-id="a2615-142">Table data objects identify rows by using an index column, a property that is guaranteed to have a unique value for each row.</span></span> <span data-ttu-id="a2615-143">大多数服务提供商使用[PidTagInstanceKey PR_INSTANCE_KEY (PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性作为索引列。 </span><span class="sxs-lookup"><span data-stu-id="a2615-143">Most service providers use the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property as the index column.</span></span> <span data-ttu-id="a2615-144">具有多个值的属性不能用作索引列。</span><span class="sxs-lookup"><span data-stu-id="a2615-144">Properties that have multiple values cannot be used as an index column.</span></span>
  
<span data-ttu-id="a2615-145">无论受更改或删除影响的行数如何，表数据对象都会生成单个通知。</span><span class="sxs-lookup"><span data-stu-id="a2615-145">Table data objects generate a single notification regardless of the number of rows affected by a change or deletion.</span></span> <span data-ttu-id="a2615-146">如果操作中的目标行不存在，则添加一行。</span><span class="sxs-lookup"><span data-stu-id="a2615-146">If a target row in an operation does not exist, a row is added.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a2615-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2615-147">See also</span></span>



[<span data-ttu-id="a2615-148">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="a2615-148">MAPI Interfaces</span></span>](mapi-interfaces.md)

