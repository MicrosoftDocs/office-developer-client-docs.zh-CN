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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7845238722ce81b84210b6f4fc33f9df0abacc07
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412021"
---
# <a name="imapicontainergetsearchcriteria"></a><span data-ttu-id="07149-103">IMAPIContainer::GetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="07149-103">IMAPIContainer::GetSearchCriteria</span></span>

  
  
<span data-ttu-id="07149-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07149-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07149-105">获取容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="07149-105">Obtains the search criteria for the container.</span></span>
  
```cpp
HRESULT GetSearchCriteria(
  ULONG ulFlags,
  LPSRestriction FAR * lppRestriction,
  LPENTRYLIST FAR * lppContainerList,
  ULONG FAR * lpulSearchState
);
```

## <a name="parameters"></a><span data-ttu-id="07149-106">参数</span><span class="sxs-lookup"><span data-stu-id="07149-106">Parameters</span></span>

 <span data-ttu-id="07149-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="07149-107">_ulFlags_</span></span>
  
> <span data-ttu-id="07149-108">[in]控制传入字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="07149-108">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="07149-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="07149-109">The following flag can be set:</span></span>
    
<span data-ttu-id="07149-110">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="07149-110">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="07149-111">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="07149-111">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="07149-112">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="07149-112">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="07149-113">_lppRestriction_</span><span class="sxs-lookup"><span data-stu-id="07149-113">_lppRestriction_</span></span>
  
> <span data-ttu-id="07149-114">[out]指向定义搜索条件的 [SRestriction](srestriction.md) 结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="07149-114">[out] A pointer to a pointer to an [SRestriction](srestriction.md) structure that defines the search criteria.</span></span> <span data-ttu-id="07149-115">如果客户端应用程序在  _lppRestriction_ 参数中传递 NULL， **则 GetSearchCriteria** 不会返回 **SRestriction** 结构。</span><span class="sxs-lookup"><span data-stu-id="07149-115">If a client application passes NULL in the  _lppRestriction_ parameter, **GetSearchCriteria** does not return an **SRestriction** structure.</span></span> 
    
 <span data-ttu-id="07149-116">_lppContainerList_</span><span class="sxs-lookup"><span data-stu-id="07149-116">_lppContainerList_</span></span>
  
> <span data-ttu-id="07149-117">[out]指向指向表示要包含在搜索中的容器的条目标识符数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="07149-117">[out] A pointer to a pointer to an array of entry identifiers that represent containers to be included in the search.</span></span> <span data-ttu-id="07149-118">如果客户端在  _lppContainerList_ 参数中传递 NULL， **则 GetSearchCriteria** 不会返回条目标识符数组。</span><span class="sxs-lookup"><span data-stu-id="07149-118">If a client passes NULL in the  _lppContainerList_ parameter, **GetSearchCriteria** does not return an array of entry identifiers.</span></span> 
    
 <span data-ttu-id="07149-119">_lpulSearchState_</span><span class="sxs-lookup"><span data-stu-id="07149-119">_lpulSearchState_</span></span>
  
> <span data-ttu-id="07149-120">[out]指向用于指示搜索当前状态的标志的位掩码的指针。</span><span class="sxs-lookup"><span data-stu-id="07149-120">[out] A pointer to a bitmask of flags used to indicate the current state of the search.</span></span> <span data-ttu-id="07149-121">如果客户端在  _lpulSearchState_ 参数中传递 NULL， **则 GetSearchCriteria** 不返回任何标志。</span><span class="sxs-lookup"><span data-stu-id="07149-121">If a client passes NULL in the  _lpulSearchState_ parameter, **GetSearchCriteria** returns no flags.</span></span> <span data-ttu-id="07149-122">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="07149-122">The following flags can be set:</span></span> 
    
<span data-ttu-id="07149-123">SEARCH_FOREGROUND</span><span class="sxs-lookup"><span data-stu-id="07149-123">SEARCH_FOREGROUND</span></span> 
  
> <span data-ttu-id="07149-124">搜索应相对于其他搜索以高优先级运行。</span><span class="sxs-lookup"><span data-stu-id="07149-124">The search should run at high priority relative to other searches.</span></span> <span data-ttu-id="07149-125">如果未设置此标志，则相对于其他搜索以正常优先级运行搜索。</span><span class="sxs-lookup"><span data-stu-id="07149-125">If this flag is not set, the search runs at normal priority relative to other searches.</span></span>
    
<span data-ttu-id="07149-126">SEARCH_REBUILD</span><span class="sxs-lookup"><span data-stu-id="07149-126">SEARCH_REBUILD</span></span> 
  
> <span data-ttu-id="07149-127">搜索将进入其操作占用大量 CPU 的模式，尝试查找与条件匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="07149-127">The search is in the CPU-intensive mode of its operation, trying to locate messages that match the criteria.</span></span> <span data-ttu-id="07149-128">如果未设置此标志，则搜索操作中占用大量 CPU 的部分将结束。</span><span class="sxs-lookup"><span data-stu-id="07149-128">If this flag is not set, the CPU-intensive part of the search's operation is over.</span></span> <span data-ttu-id="07149-129">此标志仅在搜索处于活动状态（ (，即，如果SEARCH_RUNNING设置该标记) 。</span><span class="sxs-lookup"><span data-stu-id="07149-129">This flag has meaning only if the search is active (that is, if the SEARCH_RUNNING flag is set).</span></span>
    
<span data-ttu-id="07149-130">SEARCH_RECURSIVE</span><span class="sxs-lookup"><span data-stu-id="07149-130">SEARCH_RECURSIVE</span></span> 
  
> <span data-ttu-id="07149-131">搜索在指定的容器及其所有子容器中查找匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="07149-131">The search is looking in specified containers and all their child containers for matching entries.</span></span> <span data-ttu-id="07149-132">如果未设置此标志，则仅搜索上次调用 [IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) 方法时显式包含的容器。</span><span class="sxs-lookup"><span data-stu-id="07149-132">If this flag is not set, only the containers explicitly included in the last call to the [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) method are being searched.</span></span> 
    
<span data-ttu-id="07149-133">SEARCH_RUNNING</span><span class="sxs-lookup"><span data-stu-id="07149-133">SEARCH_RUNNING</span></span> 
  
> <span data-ttu-id="07149-134">搜索处于活动状态，并且正在更新容器的内容表以反映邮件存储或通讯簿中的更改。</span><span class="sxs-lookup"><span data-stu-id="07149-134">The search is active and the container's contents table is being updated to reflect changes in the message store or address book.</span></span> <span data-ttu-id="07149-135">如果未设置此标志，则搜索将处于非活动状态，并且内容表是静态的。</span><span class="sxs-lookup"><span data-stu-id="07149-135">If this flag is not set, the search is inactive and the contents table is static.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="07149-136">返回值</span><span class="sxs-lookup"><span data-stu-id="07149-136">Return value</span></span>

<span data-ttu-id="07149-137">S_OK</span><span class="sxs-lookup"><span data-stu-id="07149-137">S_OK</span></span> 
  
> <span data-ttu-id="07149-138">已成功获取搜索条件。</span><span class="sxs-lookup"><span data-stu-id="07149-138">The search criteria was successfully obtained.</span></span>
    
<span data-ttu-id="07149-139">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="07149-139">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="07149-140">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="07149-140">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="07149-141">MAPI_E_NOT_INITIALIZED</span><span class="sxs-lookup"><span data-stu-id="07149-141">MAPI_E_NOT_INITIALIZED</span></span> 
  
> <span data-ttu-id="07149-142">从未为容器建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="07149-142">Search criteria were never established for the container.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="07149-143">备注</span><span class="sxs-lookup"><span data-stu-id="07149-143">Remarks</span></span>

<span data-ttu-id="07149-144">**IMAPIContainer：：GetSearchCriteria** 方法获取支持搜索的容器（通常为搜索结果文件夹）的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="07149-144">The **IMAPIContainer::GetSearchCriteria** method obtains the search criteria for a container that supports searches, typically a search-results folder.</span></span> <span data-ttu-id="07149-145">通过调用容器的 **IMAPIContainer：：SetSearchCriteria 方法创建搜索** 条件。</span><span class="sxs-lookup"><span data-stu-id="07149-145">You create search criteria by calling a container's **IMAPIContainer::SetSearchCriteria** method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="07149-146">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="07149-146">Notes to implementers</span></span>

<span data-ttu-id="07149-147">只有在提供与 PR_SEARCH ([PidTagSearch](pidtagsearch-canonical-property.md)属性关联的高级搜索功能时，通讯簿容器才可能需要支持 **GetSearchCriteria**) 。</span><span class="sxs-lookup"><span data-stu-id="07149-147">Address book containers may need to support **GetSearchCriteria** only if they provide the advanced search capabilities associated with the **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) property.</span></span> <span data-ttu-id="07149-148">若要详细了解如何实现通讯簿容器的高级搜索功能，请参阅 [实现高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="07149-148">For more information about how to implement the advanced search feature for address book containers, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="07149-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="07149-149">Notes to callers</span></span>

<span data-ttu-id="07149-150">完成 _lppRestriction_ 和 _lppContainerList_ 参数指向的数据结构后，请针对要释放的每个结构调用一次 [MAPIFreeBuffer。](mapifreebuffer.md)</span><span class="sxs-lookup"><span data-stu-id="07149-150">When you are finished with the data structures pointed to by the  _lppRestriction_ and  _lppContainerList_ parameters, call [MAPIFreeBuffer](mapifreebuffer.md) once for each structure to be released.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="07149-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="07149-151">MFCMAPI reference</span></span>

<span data-ttu-id="07149-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="07149-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="07149-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="07149-153">**File**</span></span>|<span data-ttu-id="07149-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="07149-154">**Function**</span></span>|<span data-ttu-id="07149-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="07149-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07149-156">HierarchyTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="07149-156">HierarchyTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="07149-157">CHierarchyTableDlg：：OnEditSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="07149-157">CHierarchyTableDlg::OnEditSearchCriteria</span></span>  <br/> |<span data-ttu-id="07149-158">MFCMAPI 使用 **IMAPIContainer：：GetSearchCriteria** 方法从要显示的文件夹获取搜索条件。</span><span class="sxs-lookup"><span data-stu-id="07149-158">MFCMAPI uses the **IMAPIContainer::GetSearchCriteria** method to obtain search criteria from a folder to display.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07149-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07149-159">See also</span></span>



[<span data-ttu-id="07149-160">IMAPIContainer::SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="07149-160">IMAPIContainer::SetSearchCriteria</span></span>](imapicontainer-setsearchcriteria.md)
  
[<span data-ttu-id="07149-161">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="07149-161">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
  
[<span data-ttu-id="07149-162">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="07149-162">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="07149-163">PidTagSearch 规范属性</span><span class="sxs-lookup"><span data-stu-id="07149-163">PidTagSearch Canonical Property</span></span>](pidtagsearch-canonical-property.md)
  
[<span data-ttu-id="07149-164">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="07149-164">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="07149-165">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="07149-165">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

