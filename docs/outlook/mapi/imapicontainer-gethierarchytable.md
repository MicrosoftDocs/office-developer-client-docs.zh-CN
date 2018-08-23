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
ms.openlocfilehash: 88b6f220f812f419b3f881aaa7f70a22186b589e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563798"
---
# <a name="imapicontainergethierarchytable"></a><span data-ttu-id="721eb-103">IMAPIContainer::GetHierarchyTable</span><span class="sxs-lookup"><span data-stu-id="721eb-103">IMAPIContainer::GetHierarchyTable</span></span>

  
  
<span data-ttu-id="721eb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="721eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="721eb-105">返回到容器的层次结构表的指针。</span><span class="sxs-lookup"><span data-stu-id="721eb-105">Returns a pointer to the container's hierarchy table.</span></span>
  
```cpp
HRESULT GetHierarchyTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="721eb-106">参数</span><span class="sxs-lookup"><span data-stu-id="721eb-106">Parameters</span></span>

 <span data-ttu-id="721eb-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="721eb-107">_ulFlags_</span></span>
  
> <span data-ttu-id="721eb-108">[in]位掩码的标志，控制如何将信息返回表中。</span><span class="sxs-lookup"><span data-stu-id="721eb-108">[in] A bitmask of flags that controls how information is returned in the table.</span></span> <span data-ttu-id="721eb-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="721eb-109">The following flags can be set:</span></span>
    
<span data-ttu-id="721eb-110">CONVENIENT_DEPTH</span><span class="sxs-lookup"><span data-stu-id="721eb-110">CONVENIENT_DEPTH</span></span> 
  
> <span data-ttu-id="721eb-111">用来自多个级别的容器中填充的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="721eb-111">Fills the hierarchy table with containers from multiple levels.</span></span> <span data-ttu-id="721eb-112">如果未设置 CONVENIENT_DEPTH，层次结构表包含仅容器的直接子容器。</span><span class="sxs-lookup"><span data-stu-id="721eb-112">If CONVENIENT_DEPTH is not set, the hierarchy table contains only the container's immediate child containers.</span></span>
    
<span data-ttu-id="721eb-113">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="721eb-113">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="721eb-114">**通讯**可以成功，可能之前返回表可用于将呼叫者。</span><span class="sxs-lookup"><span data-stu-id="721eb-114">**GetHierarchyTable** can return successfully, possibly before the table is made available to the caller.</span></span> <span data-ttu-id="721eb-115">如果表不可用，则进行后续表呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="721eb-115">If the table is not available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="721eb-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="721eb-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="721eb-117">Unicode 格式返回包含字符串数据的列的请求。</span><span class="sxs-lookup"><span data-stu-id="721eb-117">Requests that the columns that contain string data be returned in Unicode format.</span></span> <span data-ttu-id="721eb-118">如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式返回字符串。</span><span class="sxs-lookup"><span data-stu-id="721eb-118">If the MAPI_UNICODE flag is not set, the strings should be returned in ANSI format.</span></span> 
    
<span data-ttu-id="721eb-119">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="721eb-119">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="721eb-120">显示项目的当前标记为软删除 — 即，它们是中已删除的邮件保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="721eb-120">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="721eb-121">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="721eb-121">_lppTable_</span></span>
  
> <span data-ttu-id="721eb-122">[输出]指向与层次结构表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="721eb-122">[out] A pointer to a pointer to the hierarchy table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="721eb-123">返回值</span><span class="sxs-lookup"><span data-stu-id="721eb-123">Return value</span></span>

<span data-ttu-id="721eb-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="721eb-124">S_OK</span></span> 
  
> <span data-ttu-id="721eb-125">已成功检索层次结构表。</span><span class="sxs-lookup"><span data-stu-id="721eb-125">The hierarchy table was successfully retrieved.</span></span>
    
<span data-ttu-id="721eb-126">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="721eb-126">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="721eb-127">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="721eb-127">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="721eb-128">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="721eb-128">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="721eb-129">容器具有没有子容器，并不能提供层次结构表。</span><span class="sxs-lookup"><span data-stu-id="721eb-129">The container has no child containers and cannot provide a hierarchy table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="721eb-130">注解</span><span class="sxs-lookup"><span data-stu-id="721eb-130">Remarks</span></span>

<span data-ttu-id="721eb-131">**IMAPIContainer::GetHierarchyTable**方法返回到容器的层次结构表的指针。</span><span class="sxs-lookup"><span data-stu-id="721eb-131">The **IMAPIContainer::GetHierarchyTable** method returns a pointer to the hierarchy table of a container.</span></span> <span data-ttu-id="721eb-132">层次结构表包含有关容器中的子容器的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="721eb-132">A hierarchy table holds summary information about the child containers in the container.</span></span> <span data-ttu-id="721eb-133">文件夹层次结构表子文件夹; 有关保留的信息通讯簿层次结构表保留信息子地址簿容器和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="721eb-133">Folder hierarchy tables hold information about subfolders; address book hierarchy tables hold information about child address book containers and distribution lists.</span></span> 
  
<span data-ttu-id="721eb-134">很可能为一些容器具有没有子容器。</span><span class="sxs-lookup"><span data-stu-id="721eb-134">It is possible for some containers to have no child containers.</span></span> <span data-ttu-id="721eb-135">这些容器返回 MAPI_E_NO_SUPPORT 从**通讯**其实现。</span><span class="sxs-lookup"><span data-stu-id="721eb-135">These containers return MAPI_E_NO_SUPPORT from their implementations of **GetHierarchyTable**.</span></span>
  
<span data-ttu-id="721eb-136">当设置 CONVENIENT_DEPTH 标志时，层次结构表中的各行还作为列包含**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="721eb-136">When the CONVENIENT_DEPTH flag is set, each row in the hierarchy table also includes the **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md)) property as a column.</span></span> <span data-ttu-id="721eb-137">**PR_DEPTH**指示相对于容器实现表的每个容器的级别。</span><span class="sxs-lookup"><span data-stu-id="721eb-137">**PR_DEPTH** indicates the level of each container relative to the container that implements the table.</span></span> <span data-ttu-id="721eb-138">实施容器的直接子容器位于深度零，零深度容器中的子容器的深度，依此类推。</span><span class="sxs-lookup"><span data-stu-id="721eb-138">The implementing container's immediate child containers are at depth zero, child containers in the zero depth containers are at depth one, and so on.</span></span> <span data-ttu-id="721eb-139">**PR_DEPTH**的值增加按顺序的层次结构级别深化。</span><span class="sxs-lookup"><span data-stu-id="721eb-139">The values of **PR_DEPTH** increase sequentially as the hierarchy of levels deepens.</span></span> 
  
<span data-ttu-id="721eb-140">必需的和可选层次结构表中的列的完整列表，请参阅[层次结构表](hierarchy-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="721eb-140">For a complete list of required and optional columns in hierarchy tables, see [Hierarchy Tables](hierarchy-tables.md).</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="721eb-141">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="721eb-141">Notes to implementers</span></span>

<span data-ttu-id="721eb-142">如果您支持您的容器层次结构表，还必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="721eb-142">If you support a hierarchy table for your container, you must also do the following:</span></span>
  
- <span data-ttu-id="721eb-143">支持对容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法的调用，以打开**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="721eb-143">Support a call to the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="721eb-144">返回**PR_CONTAINER_HIERARCHY**中容器的[IMAPIProp::GetPropList](imapiprop-getproplist.md)或[IMAPIProp::GetProps](imapiprop-getprops.md)方法调用。</span><span class="sxs-lookup"><span data-stu-id="721eb-144">Return **PR_CONTAINER_HIERARCHY** from a call to the container's [IMAPIProp::GetPropList](imapiprop-getproplist.md) or [IMAPIProp::GetProps](imapiprop-getprops.md) methods.</span></span> 
    
## <a name="notes-to-callers"></a><span data-ttu-id="721eb-145">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="721eb-145">Notes to callers</span></span>

<span data-ttu-id="721eb-146">可以截断字符串和二进制内容表格列。</span><span class="sxs-lookup"><span data-stu-id="721eb-146">String and binary contents table columns can be truncated.</span></span> <span data-ttu-id="721eb-147">通常情况下，提供程序返回 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="721eb-147">Typically, providers return 255 characters.</span></span> <span data-ttu-id="721eb-148">因为您无法知道提前是否表包含截断的列，假定一列被截断如果列的长度为 255 个或 510 字节。</span><span class="sxs-lookup"><span data-stu-id="721eb-148">Because you cannot know beforehand whether a table includes truncated columns, assume that a column is truncated if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="721eb-149">直接从通过使用其条目标识符来打开它，然后调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法的对象，总是可以检索有必要，截断列中的完整值。</span><span class="sxs-lookup"><span data-stu-id="721eb-149">You can always retrieve the full value of a truncated column, if necessary, directly from the object by using its entry identifier to open it and then calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
<span data-ttu-id="721eb-150">具体取决于提供程序的实现、 限制和排序操作可以应用到整个字符串或该字符串的截断版本。</span><span class="sxs-lookup"><span data-stu-id="721eb-150">Depending on the provider's implementation, restrictions and sorting operations can apply to the whole string or to the truncated version of that string.</span></span> <span data-ttu-id="721eb-151">此外，存储提供程序不能保证服从的设置的排序顺序[SSortOrderSet](ssortorderset.md)指定层次结构表。</span><span class="sxs-lookup"><span data-stu-id="721eb-151">Moreover, store providers are not guaranteed to honor the sort order set [SSortOrderSet](ssortorderset.md) specified for hierarchy tables.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="721eb-152">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="721eb-152">MFCMAPI reference</span></span>

<span data-ttu-id="721eb-153">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="721eb-153">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="721eb-154">**文件**</span><span class="sxs-lookup"><span data-stu-id="721eb-154">**File**</span></span>|<span data-ttu-id="721eb-155">**函数**</span><span class="sxs-lookup"><span data-stu-id="721eb-155">**Function**</span></span>|<span data-ttu-id="721eb-156">**Comment**</span><span class="sxs-lookup"><span data-stu-id="721eb-156">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="721eb-157">HierarchyTableTreeCtrl.cpp</span><span class="sxs-lookup"><span data-stu-id="721eb-157">HierarchyTableTreeCtrl.cpp</span></span>  <br/> |<span data-ttu-id="721eb-158">CHierarchyTableTreeCtrl::GetHierarchyTable</span><span class="sxs-lookup"><span data-stu-id="721eb-158">CHierarchyTableTreeCtrl::GetHierarchyTable</span></span>  <br/> |<span data-ttu-id="721eb-159">CHierarchyTableTreeCtrl 类使用**通讯**获取要在树视图控件中显示的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="721eb-159">The CHierarchyTableTreeCtrl class uses **GetHierarchyTable** to obtain hierarchy tables to display in a tree view control.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="721eb-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="721eb-160">See also</span></span>



[<span data-ttu-id="721eb-161">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="721eb-161">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="721eb-162">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="721eb-162">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="721eb-163">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="721eb-163">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="721eb-164">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="721eb-164">PidTagContainerHierarchy Canonical Property</span></span>](pidtagcontainerhierarchy-canonical-property.md)
  
[<span data-ttu-id="721eb-165">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="721eb-165">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="721eb-166">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="721eb-166">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

