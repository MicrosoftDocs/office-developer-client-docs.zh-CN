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
ms.openlocfilehash: 968768fe75286b93bf12e349a4845fdfaa1923e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776101"
---
# <a name="itabledata--iunknown"></a><span data-ttu-id="69d6f-103">ITableData : IUnknown</span><span class="sxs-lookup"><span data-stu-id="69d6f-103">ITableData : IUnknown</span></span>

  
  
<span data-ttu-id="69d6f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="69d6f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="69d6f-105">提供用于处理表的实用程序方法。</span><span class="sxs-lookup"><span data-stu-id="69d6f-105">Provides utility methods for working with tables.</span></span> <span data-ttu-id="69d6f-106">MAPI 提供了实现**ITableData**帮助执行表维护的服务提供商的对象或表数据对象。</span><span class="sxs-lookup"><span data-stu-id="69d6f-106">MAPI provides table data objects or objects that implement **ITableData** to help service providers perform table maintenance.</span></span> <span data-ttu-id="69d6f-107">若要获取表数据对象，请服务提供商，请调用[CreateTable](createtable.md)函数。</span><span class="sxs-lookup"><span data-stu-id="69d6f-107">To obtain a table data object, service providers call the [CreateTable](createtable.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="69d6f-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="69d6f-108">Header file:</span></span>  <br/> |<span data-ttu-id="69d6f-109">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="69d6f-109">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="69d6f-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="69d6f-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="69d6f-111">表格数据对象</span><span class="sxs-lookup"><span data-stu-id="69d6f-111">Table data objects</span></span>  <br/> |
|<span data-ttu-id="69d6f-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="69d6f-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="69d6f-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="69d6f-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="69d6f-114">调用：</span><span class="sxs-lookup"><span data-stu-id="69d6f-114">Called by:</span></span>  <br/> |<span data-ttu-id="69d6f-115">服务提供商</span><span class="sxs-lookup"><span data-stu-id="69d6f-115">Service providers</span></span>  <br/> |
|<span data-ttu-id="69d6f-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="69d6f-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="69d6f-117">IID_IMAPITableData</span><span class="sxs-lookup"><span data-stu-id="69d6f-117">IID_IMAPITableData</span></span>  <br/> |
|<span data-ttu-id="69d6f-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="69d6f-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="69d6f-119">LPTABLEDATA</span><span class="sxs-lookup"><span data-stu-id="69d6f-119">LPTABLEDATA</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="69d6f-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="69d6f-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="69d6f-121">HrGetView</span><span class="sxs-lookup"><span data-stu-id="69d6f-121">HrGetView</span></span>](itabledata-hrgetview.md) <br/> |<span data-ttu-id="69d6f-122">创建表视图中，返回到[IMAPITable](imapitableiunknown.md)实现的指针。</span><span class="sxs-lookup"><span data-stu-id="69d6f-122">Creates a table view, returning a pointer to an [IMAPITable](imapitableiunknown.md) implementation.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-123">HrModifyRow</span><span class="sxs-lookup"><span data-stu-id="69d6f-123">HrModifyRow</span></span>](itabledata-hrmodifyrow.md) <br/> |<span data-ttu-id="69d6f-124">插入一个新的表格行，原因可能替换现有行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-124">Inserts a new table row, possibly replacing an existing row.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-125">HrDeleteRow</span><span class="sxs-lookup"><span data-stu-id="69d6f-125">HrDeleteRow</span></span>](itabledata-hrdeleterow.md) <br/> |<span data-ttu-id="69d6f-126">删除表格行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-126">Deletes a table row.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-127">HrQueryRow</span><span class="sxs-lookup"><span data-stu-id="69d6f-127">HrQueryRow</span></span>](itabledata-hrqueryrow.md) <br/> |<span data-ttu-id="69d6f-128">检索表格行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-128">Retrieves a table row.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-129">HrEnumRow</span><span class="sxs-lookup"><span data-stu-id="69d6f-129">HrEnumRow</span></span>](itabledata-hrenumrow.md) <br/> |<span data-ttu-id="69d6f-130">检索根据其位置表中的行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-130">Retrieves a row based on its position in the table.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-131">HrNotify</span><span class="sxs-lookup"><span data-stu-id="69d6f-131">HrNotify</span></span>](itabledata-hrnotify.md) <br/> |<span data-ttu-id="69d6f-132">发送通知的表格行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-132">Sends a notification for a table row.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-133">HrInsertRow</span><span class="sxs-lookup"><span data-stu-id="69d6f-133">HrInsertRow</span></span>](itabledata-hrinsertrow.md) <br/> |<span data-ttu-id="69d6f-134">插入表格行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-134">Inserts a table row.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-135">HrModifyRows</span><span class="sxs-lookup"><span data-stu-id="69d6f-135">HrModifyRows</span></span>](itabledata-hrmodifyrows.md) <br/> |<span data-ttu-id="69d6f-136">插入多个表行，原因可能替换现有行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-136">Inserts multiple table rows, possibly replacing existing rows.</span></span>  <br/> |
|[<span data-ttu-id="69d6f-137">HrDeleteRows</span><span class="sxs-lookup"><span data-stu-id="69d6f-137">HrDeleteRows</span></span>](itabledata-hrdeleterows.md) <br/> |<span data-ttu-id="69d6f-138">删除多个表行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-138">Deletes multiple table rows.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="69d6f-139">说明</span><span class="sxs-lookup"><span data-stu-id="69d6f-139">Remarks</span></span>

<span data-ttu-id="69d6f-140">**ITableData**的 MAPI 实现适用于按住的所有数据和任何关联的限制，在内存中，使其适合用于非常大的表的表。</span><span class="sxs-lookup"><span data-stu-id="69d6f-140">The MAPI implementation of **ITableData** works with tables by holding all of the data and any associated restrictions in memory, making it unsuitable for use with very large tables.</span></span> <span data-ttu-id="69d6f-141">不支持大型限制和复杂操作，例如分类。</span><span class="sxs-lookup"><span data-stu-id="69d6f-141">Large restrictions and complex operations such as categorization are not supported.</span></span> 
  
<span data-ttu-id="69d6f-142">表格数据对象标识行使用索引列，保证具有每个行的唯一值的属性。</span><span class="sxs-lookup"><span data-stu-id="69d6f-142">Table data objects identify rows by using an index column, a property that is guaranteed to have a unique value for each row.</span></span> <span data-ttu-id="69d6f-143">大多数服务提供商使用的索引列作为**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="69d6f-143">Most service providers use the **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) property as the index column.</span></span> <span data-ttu-id="69d6f-144">具有多个值的属性不能用作索引列。</span><span class="sxs-lookup"><span data-stu-id="69d6f-144">Properties that have multiple values cannot be used as an index column.</span></span>
  
<span data-ttu-id="69d6f-145">表格数据对象生成单个通知无论受更改或删除的行数。</span><span class="sxs-lookup"><span data-stu-id="69d6f-145">Table data objects generate a single notification regardless of the number of rows affected by a change or deletion.</span></span> <span data-ttu-id="69d6f-146">如果操作中的目标行不存在，将添加行。</span><span class="sxs-lookup"><span data-stu-id="69d6f-146">If a target row in an operation does not exist, a row is added.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="69d6f-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69d6f-147">See also</span></span>



[<span data-ttu-id="69d6f-148">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="69d6f-148">MAPI Interfaces</span></span>](mapi-interfaces.md)

