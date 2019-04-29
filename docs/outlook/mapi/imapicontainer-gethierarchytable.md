---
title: IMAPIContainerGetHierarchyTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.GetHierarchyTable
api_type:
- COM
ms.assetid: d0c54092-86a3-47e0-8133-72e119e74b65
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efc7f7a2fa703004afe361d766e0209ba40ffe46
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426196"
---
# <a name="imapicontainergethierarchytable"></a><span data-ttu-id="8e144-103">IMAPIContainer::GetHierarchyTable</span><span class="sxs-lookup"><span data-stu-id="8e144-103">IMAPIContainer::GetHierarchyTable</span></span>

  
  
<span data-ttu-id="8e144-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8e144-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8e144-105">返回指向容器的层次结构表的指针。</span><span class="sxs-lookup"><span data-stu-id="8e144-105">Returns a pointer to the container's hierarchy table.</span></span>
  
```cpp
HRESULT GetHierarchyTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="8e144-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e144-106">Parameters</span></span>

 <span data-ttu-id="8e144-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8e144-107">_ulFlags_</span></span>
  
> <span data-ttu-id="8e144-108">实时用于控制如何在表中返回信息的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8e144-108">[in] A bitmask of flags that controls how information is returned in the table.</span></span> <span data-ttu-id="8e144-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="8e144-109">The following flags can be set:</span></span>
    
<span data-ttu-id="8e144-110">CONVENIENT_DEPTH</span><span class="sxs-lookup"><span data-stu-id="8e144-110">CONVENIENT_DEPTH</span></span> 
  
> <span data-ttu-id="8e144-111">使用多个级别中的容器填充层次结构表。</span><span class="sxs-lookup"><span data-stu-id="8e144-111">Fills the hierarchy table with containers from multiple levels.</span></span> <span data-ttu-id="8e144-112">如果未设置 CONVENIENT_DEPTH, 则层次结构表仅包含容器的直接子容器。</span><span class="sxs-lookup"><span data-stu-id="8e144-112">If CONVENIENT_DEPTH is not set, the hierarchy table contains only the container's immediate child containers.</span></span>
    
<span data-ttu-id="8e144-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="8e144-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="8e144-114">在将表提供给调用程序之前, 可能会成功返回**GetHierarchyTable** 。</span><span class="sxs-lookup"><span data-stu-id="8e144-114">**GetHierarchyTable** can return successfully, possibly before the table is made available to the caller.</span></span> <span data-ttu-id="8e144-115">如果该表不可用, 则进行后续的表调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="8e144-115">If the table is not available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="8e144-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8e144-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="8e144-117">请求以 Unicode 格式返回包含字符串数据的列。</span><span class="sxs-lookup"><span data-stu-id="8e144-117">Requests that the columns that contain string data be returned in Unicode format.</span></span> <span data-ttu-id="8e144-118">如果未设置 MAPI_UNICODE 标志, 则字符串应以 ANSI 格式返回。</span><span class="sxs-lookup"><span data-stu-id="8e144-118">If the MAPI_UNICODE flag is not set, the strings should be returned in ANSI format.</span></span> 
    
<span data-ttu-id="8e144-119">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="8e144-119">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="8e144-120">显示当前标记为软删除的项目, 即它们处于 "已删除邮件" 保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="8e144-120">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="8e144-121">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="8e144-121">_lppTable_</span></span>
  
> <span data-ttu-id="8e144-122">排除指向层次结构表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8e144-122">[out] A pointer to a pointer to the hierarchy table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8e144-123">返回值</span><span class="sxs-lookup"><span data-stu-id="8e144-123">Return value</span></span>

<span data-ttu-id="8e144-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e144-124">S_OK</span></span> 
  
> <span data-ttu-id="8e144-125">已成功检索层次结构表。</span><span class="sxs-lookup"><span data-stu-id="8e144-125">The hierarchy table was successfully retrieved.</span></span>
    
<span data-ttu-id="8e144-126">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="8e144-126">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="8e144-127">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="8e144-127">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="8e144-128">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="8e144-128">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="8e144-129">容器没有子容器, 无法提供层次结构表。</span><span class="sxs-lookup"><span data-stu-id="8e144-129">The container has no child containers and cannot provide a hierarchy table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8e144-130">说明</span><span class="sxs-lookup"><span data-stu-id="8e144-130">Remarks</span></span>

<span data-ttu-id="8e144-131">**IMAPIContainer:: GetHierarchyTable**方法返回指向容器的层次结构表的指针。</span><span class="sxs-lookup"><span data-stu-id="8e144-131">The **IMAPIContainer::GetHierarchyTable** method returns a pointer to the hierarchy table of a container.</span></span> <span data-ttu-id="8e144-132">层次结构表包含容器中的子容器的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="8e144-132">A hierarchy table holds summary information about the child containers in the container.</span></span> <span data-ttu-id="8e144-133">文件夹层次结构表保留有关子文件夹的信息;通讯簿层次结构表格保存有关子通讯簿容器和通讯组列表的信息。</span><span class="sxs-lookup"><span data-stu-id="8e144-133">Folder hierarchy tables hold information about subfolders; address book hierarchy tables hold information about child address book containers and distribution lists.</span></span> 
  
<span data-ttu-id="8e144-134">有些容器可能没有子容器。</span><span class="sxs-lookup"><span data-stu-id="8e144-134">It is possible for some containers to have no child containers.</span></span> <span data-ttu-id="8e144-135">这些容器从其**GetHierarchyTable**的实现返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="8e144-135">These containers return MAPI_E_NO_SUPPORT from their implementations of **GetHierarchyTable**.</span></span>
  
<span data-ttu-id="8e144-136">设置 CONVENIENT_DEPTH 标志后, 层次结构表中的每一行也包含**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性作为一列。</span><span class="sxs-lookup"><span data-stu-id="8e144-136">When the CONVENIENT_DEPTH flag is set, each row in the hierarchy table also includes the **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) property as a column.</span></span> <span data-ttu-id="8e144-137">**PR_DEPTH**指示相对于实现表的容器的每个容器的级别。</span><span class="sxs-lookup"><span data-stu-id="8e144-137">**PR_DEPTH** indicates the level of each container relative to the container that implements the table.</span></span> <span data-ttu-id="8e144-138">实现容器的直接子容器的深度为零, 零深度容器中的子容器的深度为 1, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="8e144-138">The implementing container's immediate child containers are at depth zero, child containers in the zero depth containers are at depth one, and so on.</span></span> <span data-ttu-id="8e144-139">**PR_DEPTH**的值按级别 deepens 的层次结构增长。</span><span class="sxs-lookup"><span data-stu-id="8e144-139">The values of **PR_DEPTH** increase sequentially as the hierarchy of levels deepens.</span></span> 
  
<span data-ttu-id="8e144-140">有关层次结构表中的必填列和可选列的完整列表, 请参阅[层次结构表](hierarchy-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8e144-140">For a complete list of required and optional columns in hierarchy tables, see [Hierarchy Tables](hierarchy-tables.md).</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8e144-141">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="8e144-141">Notes to implementers</span></span>

<span data-ttu-id="8e144-142">如果您支持容器的层次结构表, 则还必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8e144-142">If you support a hierarchy table for your container, you must also do the following:</span></span>
  
- <span data-ttu-id="8e144-143">支持对容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法的调用, 以打开**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8e144-143">Support a call to the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="8e144-144">从对容器的[IMAPIProp:: GetPropList](imapiprop-getproplist.md)或[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的调用中返回**PR_CONTAINER_HIERARCHY** 。</span><span class="sxs-lookup"><span data-stu-id="8e144-144">Return **PR_CONTAINER_HIERARCHY** from a call to the container's [IMAPIProp::GetPropList](imapiprop-getproplist.md) or [IMAPIProp::GetProps](imapiprop-getprops.md) methods.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="8e144-145">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8e144-145">Notes to callers</span></span>

<span data-ttu-id="8e144-146">字符串和二进制内容表中的列可以被截断。</span><span class="sxs-lookup"><span data-stu-id="8e144-146">String and binary contents table columns can be truncated.</span></span> <span data-ttu-id="8e144-147">通常, 提供程序返回255个字符。</span><span class="sxs-lookup"><span data-stu-id="8e144-147">Typically, providers return 255 characters.</span></span> <span data-ttu-id="8e144-148">由于您无法事先知道表是否包括截断的列, 因此假定列的长度为255或510字节时, 将截断列。</span><span class="sxs-lookup"><span data-stu-id="8e144-148">Because you cannot know beforehand whether a table includes truncated columns, assume that a column is truncated if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="8e144-149">如果需要, 您始终可以从对象中直接检索已截断列的完整值, 方法是使用其条目标识符将其打开, 然后调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8e144-149">You can always retrieve the full value of a truncated column, if necessary, directly from the object by using its entry identifier to open it and then calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
<span data-ttu-id="8e144-150">根据提供程序的实现, 限制和排序操作可应用于整个字符串或该字符串的截断版本。</span><span class="sxs-lookup"><span data-stu-id="8e144-150">Depending on the provider's implementation, restrictions and sorting operations can apply to the whole string or to the truncated version of that string.</span></span> <span data-ttu-id="8e144-151">此外, 不能保证存储提供程序遵循为层次结构表指定的排序顺序设置[SSortOrderSet](ssortorderset.md) 。</span><span class="sxs-lookup"><span data-stu-id="8e144-151">Moreover, store providers are not guaranteed to honor the sort order set [SSortOrderSet](ssortorderset.md) specified for hierarchy tables.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8e144-152">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8e144-152">MFCMAPI reference</span></span>

<span data-ttu-id="8e144-153">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8e144-153">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8e144-154">**文件**</span><span class="sxs-lookup"><span data-stu-id="8e144-154">**File**</span></span>|<span data-ttu-id="8e144-155">**函数**</span><span class="sxs-lookup"><span data-stu-id="8e144-155">**Function**</span></span>|<span data-ttu-id="8e144-156">**备注**</span><span class="sxs-lookup"><span data-stu-id="8e144-156">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e144-157">HierarchyTableTreeCtrl</span><span class="sxs-lookup"><span data-stu-id="8e144-157">HierarchyTableTreeCtrl.cpp</span></span>  <br/> |<span data-ttu-id="8e144-158">CHierarchyTableTreeCtrl:: GetHierarchyTable</span><span class="sxs-lookup"><span data-stu-id="8e144-158">CHierarchyTableTreeCtrl::GetHierarchyTable</span></span>  <br/> |<span data-ttu-id="8e144-159">CHierarchyTableTreeCtrl 类使用**GetHierarchyTable**获取要在树视图控件中显示的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="8e144-159">The CHierarchyTableTreeCtrl class uses **GetHierarchyTable** to obtain hierarchy tables to display in a tree view control.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8e144-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e144-160">See also</span></span>



[<span data-ttu-id="8e144-161">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="8e144-161">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="8e144-162">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="8e144-162">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="8e144-163">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8e144-163">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="8e144-164">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="8e144-164">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="8e144-165">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8e144-165">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="8e144-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8e144-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

