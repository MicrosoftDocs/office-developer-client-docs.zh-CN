---
title: IMAPIContainerGetSearchCriteria
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.GetSearchCriteria
api_type:
- COM
ms.assetid: 41b6c162-9984-43a3-b38e-44f0afae67de
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 13c151a134e4334e8ed2e75e031a6fc9dddbf941
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775321"
---
# <a name="imapicontainergetsearchcriteria"></a><span data-ttu-id="94cb0-103">IMAPIContainer::GetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="94cb0-103">IMAPIContainer::GetSearchCriteria</span></span>

  
  
<span data-ttu-id="94cb0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="94cb0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="94cb0-105">获取容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="94cb0-105">Obtains the search criteria for the container.</span></span>
  
```cpp
HRESULT GetSearchCriteria(
  ULONG ulFlags,
  LPSRestriction FAR * lppRestriction,
  LPENTRYLIST FAR * lppContainerList,
  ULONG FAR * lpulSearchState
);
```

## <a name="parameters"></a><span data-ttu-id="94cb0-106">参数</span><span class="sxs-lookup"><span data-stu-id="94cb0-106">Parameters</span></span>

 <span data-ttu-id="94cb0-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="94cb0-107">_ulFlags_</span></span>
  
> <span data-ttu-id="94cb0-108">[in]位掩码的标志的控制传入的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="94cb0-108">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="94cb0-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="94cb0-109">The following flag can be set:</span></span>
    
<span data-ttu-id="94cb0-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="94cb0-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="94cb0-111">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="94cb0-111">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="94cb0-112">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="94cb0-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="94cb0-113">_lppRestriction_</span><span class="sxs-lookup"><span data-stu-id="94cb0-113">_lppRestriction_</span></span>
  
> <span data-ttu-id="94cb0-114">[输出]指向[SRestriction](srestriction.md)结构，定义的搜索条件的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="94cb0-114">[out] A pointer to a pointer to an [SRestriction](srestriction.md) structure that defines the search criteria.</span></span> <span data-ttu-id="94cb0-115">如果客户端应用程序中的_lppRestriction_参数传递 NULL， **GetSearchCriteria**不返回**SRestriction**结构。</span><span class="sxs-lookup"><span data-stu-id="94cb0-115">If a client application passes NULL in the  _lppRestriction_ parameter, **GetSearchCriteria** does not return an **SRestriction** structure.</span></span> 
    
 <span data-ttu-id="94cb0-116">_lppContainerList_</span><span class="sxs-lookup"><span data-stu-id="94cb0-116">_lppContainerList_</span></span>
  
> <span data-ttu-id="94cb0-117">[输出]指向为数组表示容器要包括在搜索中的项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="94cb0-117">[out] A pointer to a pointer to an array of entry identifiers that represent containers to be included in the search.</span></span> <span data-ttu-id="94cb0-118">如果客户端中_lppContainerList_参数传递 NULL， **GetSearchCriteria**不返回项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="94cb0-118">If a client passes NULL in the  _lppContainerList_ parameter, **GetSearchCriteria** does not return an array of entry identifiers.</span></span> 
    
 <span data-ttu-id="94cb0-119">_lpulSearchState_</span><span class="sxs-lookup"><span data-stu-id="94cb0-119">_lpulSearchState_</span></span>
  
> <span data-ttu-id="94cb0-120">[输出]一个指向用于指示搜索的当前状态标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="94cb0-120">[out] A pointer to a bitmask of flags used to indicate the current state of the search.</span></span> <span data-ttu-id="94cb0-121">如果客户端中_lpulSearchState_参数传递 NULL， **GetSearchCriteria**返回任何标志。</span><span class="sxs-lookup"><span data-stu-id="94cb0-121">If a client passes NULL in the  _lpulSearchState_ parameter, **GetSearchCriteria** returns no flags.</span></span> <span data-ttu-id="94cb0-122">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="94cb0-122">The following flags can be set:</span></span> 
    
<span data-ttu-id="94cb0-123">SEARCH_FOREGROUND</span><span class="sxs-lookup"><span data-stu-id="94cb0-123">SEARCH_FOREGROUND</span></span> 
  
> <span data-ttu-id="94cb0-124">搜索应运行在相对于其他搜索高优先级。</span><span class="sxs-lookup"><span data-stu-id="94cb0-124">The search should run at high priority relative to other searches.</span></span> <span data-ttu-id="94cb0-125">如果未设置此标志，则在相对于其他搜索正常优先级运行搜索。</span><span class="sxs-lookup"><span data-stu-id="94cb0-125">If this flag is not set, the search runs at normal priority relative to other searches.</span></span>
    
<span data-ttu-id="94cb0-126">SEARCH_REBUILD</span><span class="sxs-lookup"><span data-stu-id="94cb0-126">SEARCH_REBUILD</span></span> 
  
> <span data-ttu-id="94cb0-127">搜索是 CPU 密集型模式操作，尝试查找符合条件的邮件中。</span><span class="sxs-lookup"><span data-stu-id="94cb0-127">The search is in the CPU-intensive mode of its operation, trying to locate messages that match the criteria.</span></span> <span data-ttu-id="94cb0-128">如果未设置此标志，搜索操作的 CPU 密集型部分是通过。</span><span class="sxs-lookup"><span data-stu-id="94cb0-128">If this flag is not set, the CPU-intensive part of the search's operation is over.</span></span> <span data-ttu-id="94cb0-129">此标志仅当有意义搜索处于活动状态 （也就是说，如果设置了 SEARCH_RUNNING 标志）。</span><span class="sxs-lookup"><span data-stu-id="94cb0-129">This flag has meaning only if the search is active (that is, if the SEARCH_RUNNING flag is set).</span></span>
    
<span data-ttu-id="94cb0-130">SEARCH_RECURSIVE</span><span class="sxs-lookup"><span data-stu-id="94cb0-130">SEARCH_RECURSIVE</span></span> 
  
> <span data-ttu-id="94cb0-131">搜索查找指定的容器的匹配项的所有及其子容器中。</span><span class="sxs-lookup"><span data-stu-id="94cb0-131">The search is looking in specified containers and all their child containers for matching entries.</span></span> <span data-ttu-id="94cb0-132">如果未设置此标志，正在搜索仅[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的最后一个呼叫中明确包括的容器。</span><span class="sxs-lookup"><span data-stu-id="94cb0-132">If this flag is not set, only the containers explicitly included in the last call to the [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method are being searched.</span></span> 
    
<span data-ttu-id="94cb0-133">SEARCH_RUNNING</span><span class="sxs-lookup"><span data-stu-id="94cb0-133">SEARCH_RUNNING</span></span> 
  
> <span data-ttu-id="94cb0-134">搜索处于活动状态且容器的内容表正在更新以反映邮件存储区中的更改或通讯簿。</span><span class="sxs-lookup"><span data-stu-id="94cb0-134">The search is active and the container's contents table is being updated to reflect changes in the message store or address book.</span></span> <span data-ttu-id="94cb0-135">如果未设置此标志，搜索处于非活动状态并将目录是静态的。</span><span class="sxs-lookup"><span data-stu-id="94cb0-135">If this flag is not set, the search is inactive and the contents table is static.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="94cb0-136">返回值</span><span class="sxs-lookup"><span data-stu-id="94cb0-136">Return value</span></span>

<span data-ttu-id="94cb0-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="94cb0-137">S_OK</span></span> 
  
> <span data-ttu-id="94cb0-138">成功获取的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="94cb0-138">The search criteria was successfully obtained.</span></span>
    
<span data-ttu-id="94cb0-139">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="94cb0-139">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="94cb0-140">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="94cb0-140">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="94cb0-141">MAPI_E_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="94cb0-141">MAPI_E_NOT_INITIALIZED</span></span> 
  
> <span data-ttu-id="94cb0-142">搜索条件从不已建立的容器。</span><span class="sxs-lookup"><span data-stu-id="94cb0-142">Search criteria were never established for the container.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="94cb0-143">备注</span><span class="sxs-lookup"><span data-stu-id="94cb0-143">Remarks</span></span>

<span data-ttu-id="94cb0-144">**IMAPIContainer::GetSearchCriteria**方法获取支持搜索，通常为一个搜索结果文件夹的容器中的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="94cb0-144">The **IMAPIContainer::GetSearchCriteria** method obtains the search criteria for a container that supports searches, typically a search-results folder.</span></span> <span data-ttu-id="94cb0-145">通过调用容器的**IMAPIContainer::SetSearchCriteria**方法创建搜索条件。</span><span class="sxs-lookup"><span data-stu-id="94cb0-145">You create search criteria by calling a container's **IMAPIContainer::SetSearchCriteria** method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="94cb0-146">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="94cb0-146">Notes to implementers</span></span>

<span data-ttu-id="94cb0-147">通讯簿容器可能需要支持**GetSearchCriteria** ，仅当它们提供与**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性关联的高级的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="94cb0-147">Address book containers may need to support **GetSearchCriteria** only if they provide the advanced search capabilities associated with the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property.</span></span> <span data-ttu-id="94cb0-148">有关如何实施通讯簿容器的高级的搜索功能的详细信息，请参阅[实现高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="94cb0-148">For more information about how to implement the advanced search feature for address book containers, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="94cb0-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="94cb0-149">Notes to callers</span></span>

<span data-ttu-id="94cb0-150">在完成时与指向由_lppRestriction_和_lppContainerList_参数的数据结构，调用[MAPIFreeBuffer](mapifreebuffer.md)一次为每个结构必须释放。</span><span class="sxs-lookup"><span data-stu-id="94cb0-150">When you are finished with the data structures pointed to by the  _lppRestriction_ and  _lppContainerList_ parameters, call [MAPIFreeBuffer](mapifreebuffer.md) once for each structure to be released.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="94cb0-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="94cb0-151">MFCMAPI reference</span></span>

<span data-ttu-id="94cb0-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="94cb0-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="94cb0-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="94cb0-153">**File**</span></span>|<span data-ttu-id="94cb0-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="94cb0-154">**Function**</span></span>|<span data-ttu-id="94cb0-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="94cb0-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94cb0-156">HierarchyTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="94cb0-156">HierarchyTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="94cb0-157">CHierarchyTableDlg::OnEditSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="94cb0-157">CHierarchyTableDlg::OnEditSearchCriteria</span></span>  <br/> |<span data-ttu-id="94cb0-158">MFCMAPI 使用**IMAPIContainer::GetSearchCriteria**方法获取从文件夹显示的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="94cb0-158">MFCMAPI uses the **IMAPIContainer::GetSearchCriteria** method to obtain search criteria from a folder to display.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="94cb0-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94cb0-159">See also</span></span>



[<span data-ttu-id="94cb0-160">IMAPIContainer::SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="94cb0-160">IMAPIContainer::SetSearchCriteria</span></span>](imapicontainer-setsearchcriteria.md)
  
[<span data-ttu-id="94cb0-161">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="94cb0-161">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
  
[<span data-ttu-id="94cb0-162">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="94cb0-162">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="94cb0-163">PidTagSearch 规范属性</span><span class="sxs-lookup"><span data-stu-id="94cb0-163">PidTagSearch Canonical Property</span></span>](pidtagsearch-canonical-property.md)
  
[<span data-ttu-id="94cb0-164">IMAPIContainer: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="94cb0-164">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="94cb0-165">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="94cb0-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

