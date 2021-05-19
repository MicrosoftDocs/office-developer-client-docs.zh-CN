---
title: IMAPIContainerSetSearchCriteria
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.SetSearchCriteria
api_type:
- COM
ms.assetid: b5eb1841-e450-4024-aeaa-3b5a492ddb99
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a6168e8fced2fff3a7f9d273e47ed2410ac4c010
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427197"
---
# <a name="imapicontainersetsearchcriteria"></a><span data-ttu-id="8dc1e-103">IMAPIContainer::SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="8dc1e-103">IMAPIContainer::SetSearchCriteria</span></span>

  
  
<span data-ttu-id="8dc1e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8dc1e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8dc1e-105">为容器建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-105">Establishes search criteria for the container.</span></span>
  
```cpp
HRESULT SetSearchCriteria(
  LPSRestriction lpRestriction,
  LPENTRYLIST lpContainerList,
  ULONG ulSearchFlags
);
```

## <a name="parameters"></a><span data-ttu-id="8dc1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="8dc1e-106">Parameters</span></span>

 <span data-ttu-id="8dc1e-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="8dc1e-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="8dc1e-108">[in]指向定义 [搜索条件的 SRestriction](srestriction.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-108">[in] A pointer to an [SRestriction](srestriction.md) structure that defines the search criteria.</span></span> <span data-ttu-id="8dc1e-109">如果在  _lpRestriction_ 参数中传递 NULL，则再次使用最近用于此容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-109">If NULL is passed in the  _lpRestriction_ parameter, the search criteria that were used most recently for this container are used again.</span></span> <span data-ttu-id="8dc1e-110">对于容器中的第一个搜索，不应在  _lpRestriction_ 中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-110">NULL should not be passed in  _lpRestriction_ for the first search in a container.</span></span> 
    
 <span data-ttu-id="8dc1e-111">_lpContainerList_</span><span class="sxs-lookup"><span data-stu-id="8dc1e-111">_lpContainerList_</span></span>
  
> <span data-ttu-id="8dc1e-112">[in]指向表示要包含在搜索中的容器的条目标识符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-112">[in] A pointer to an array of entry identifiers that represent containers to be included in the search.</span></span> <span data-ttu-id="8dc1e-113">如果客户端在  _lpContainerList_ 参数中传递 NULL，则最近用于搜索此容器的条目标识符将用于新搜索。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-113">If a client passes NULL in the  _lpContainerList_ parameter, the entry identifiers used most recently to search this container are used for the new search.</span></span> <span data-ttu-id="8dc1e-114">对于容器中的第一个搜索，客户端不应在  _lpContainerList_ 中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-114">A client should not pass NULL in  _lpContainerList_ for the first search in a container.</span></span> 
    
 <span data-ttu-id="8dc1e-115">_ulSearchFlags_</span><span class="sxs-lookup"><span data-stu-id="8dc1e-115">_ulSearchFlags_</span></span>
  
> <span data-ttu-id="8dc1e-116">[in]控制搜索执行方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-116">[in] A bitmask of flags that control how the search is performed.</span></span> <span data-ttu-id="8dc1e-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8dc1e-117">The following flags can be set:</span></span>
    
<span data-ttu-id="8dc1e-118">BACKGROUND_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-118">BACKGROUND_SEARCH</span></span> 
  
> <span data-ttu-id="8dc1e-119">相对于其他搜索，搜索应按正常优先级运行。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-119">The search should run at normal priority relative to other searches.</span></span> <span data-ttu-id="8dc1e-120">不能同时设置此标志和 FOREGROUND_SEARCH 标志。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-120">This flag cannot be set at the same time as the FOREGROUND_SEARCH flag.</span></span>
    
<span data-ttu-id="8dc1e-121">FOREGROUND_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-121">FOREGROUND_SEARCH</span></span> 
  
> <span data-ttu-id="8dc1e-122">搜索应相对于其他搜索以高优先级运行。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-122">The search should run at high priority relative to other searches.</span></span> <span data-ttu-id="8dc1e-123">不能同时设置此标志和 BACKGROUND_SEARCH 标志。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-123">This flag cannot be set at the same time as the BACKGROUND_SEARCH flag.</span></span>
    
<span data-ttu-id="8dc1e-124">NON_CONTENT_INDEXED_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-124">NON_CONTENT_INDEXED_SEARCH</span></span>
  
> <span data-ttu-id="8dc1e-125">搜索不应使用内容索引来查找匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-125">The search should not use content indexing to find matching entries.</span></span> <span data-ttu-id="8dc1e-126">此标志仅对应用商店Exchange有效。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-126">This flag is only valid for Exchange stores.</span></span>
    
<span data-ttu-id="8dc1e-127">RECURSIVE_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-127">RECURSIVE_SEARCH</span></span> 
  
> <span data-ttu-id="8dc1e-128">搜索应包括在  _lpContainerList_ 参数中指定的容器及其所有子容器。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-128">The search should include the containers specified in the  _lpContainerList_ parameter and all their child containers.</span></span> <span data-ttu-id="8dc1e-129">不能同时设置此标志和 SHALLOW_SEARCH 标志。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-129">This flag cannot be set at the same time as the SHALLOW_SEARCH flag.</span></span> 
    
<span data-ttu-id="8dc1e-130">RESTART_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-130">RESTART_SEARCH</span></span> 
  
> <span data-ttu-id="8dc1e-131">如果这是对 **SetSearchCriteria** 的首次调用，应启动搜索;如果搜索处于非活动状态，则重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-131">The search should be initiated if this is the first call to **SetSearchCriteria**, or restarted if the search is inactive.</span></span> <span data-ttu-id="8dc1e-132">不能同时设置此标志和 STOP_SEARCH 标志。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-132">This flag cannot be set at the same time as the STOP_SEARCH flag.</span></span>
    
<span data-ttu-id="8dc1e-133">SHALLOW_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-133">SHALLOW_SEARCH</span></span> 
  
> <span data-ttu-id="8dc1e-134">搜索应仅在  _lpContainerList_ 参数中指定的容器中查找匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-134">The search should look only in the containers specified in the  _lpContainerList_ parameter for matching entries.</span></span> <span data-ttu-id="8dc1e-135">不能同时设置此标志和 RECURSIVE_SEARCH 标记。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-135">This flag cannot be set at the same time as the RECURSIVE_SEARCH flag.</span></span> 
    
<span data-ttu-id="8dc1e-136">STOP_SEARCH</span><span class="sxs-lookup"><span data-stu-id="8dc1e-136">STOP_SEARCH</span></span> 
  
> <span data-ttu-id="8dc1e-137">应停止搜索。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-137">The search should be stopped.</span></span> <span data-ttu-id="8dc1e-138">不能同时设置此标志和 RESTART_SEARCH 标志。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-138">This flag cannot be set at the same time as the RESTART_SEARCH flag.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8dc1e-139">返回值</span><span class="sxs-lookup"><span data-stu-id="8dc1e-139">Return value</span></span>

<span data-ttu-id="8dc1e-140">S_OK</span><span class="sxs-lookup"><span data-stu-id="8dc1e-140">S_OK</span></span> 
  
> <span data-ttu-id="8dc1e-141">已成功设置搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-141">The search criteria was successfully set.</span></span>
    
<span data-ttu-id="8dc1e-142">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="8dc1e-142">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="8dc1e-143">服务提供商不支持指定的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-143">The service provider does not support the specified search criteria.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8dc1e-144">备注</span><span class="sxs-lookup"><span data-stu-id="8dc1e-144">Remarks</span></span>

<span data-ttu-id="8dc1e-145">**IMAPIContainer：：SetSearchCriteria** 方法为支持搜索的容器（通常为搜索结果文件夹）建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-145">The **IMAPIContainer::SetSearchCriteria** method establishes search criteria for a container that supports searches, typically a search-results folder.</span></span> <span data-ttu-id="8dc1e-146">搜索结果文件夹包含指向符合搜索条件的邮件的链接;实际邮件仍存储在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-146">A search-results folder contains links to the messages that meet the search criteria; the actual messages are still stored in their original locations.</span></span> <span data-ttu-id="8dc1e-147">搜索结果文件夹中包含的唯一唯一数据是其内容表。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-147">The only unique data that is contained in a search-results folder is its contents table.</span></span> <span data-ttu-id="8dc1e-148">应用搜索限制后，搜索结果文件夹的内容表包含邮件存储的合并内容。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-148">The contents table of a search-results folder has the merged contents of the message store after the search restriction has been applied.</span></span> 
  
<span data-ttu-id="8dc1e-149">搜索操作仅适用于此合并的内容表;它不会搜索其他搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-149">A search operation works only on this merged contents table; it does not search through other search-results folders.</span></span> <span data-ttu-id="8dc1e-150">搜索结果仅返回与搜索条件匹配的邮件;不返回文件夹层次结构。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-150">The search results return only the messages that match the search criteria; the folder hierarchy is not returned.</span></span>
  
<span data-ttu-id="8dc1e-151">搜索完成后，控制权将返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-151">Control is returned to the client when the search has finished.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8dc1e-152">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="8dc1e-152">Notes to implementers</span></span>

<span data-ttu-id="8dc1e-153">通讯簿容器通过向内容表应用限制来建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-153">Address book containers establish search criteria by applying restrictions to their contents tables.</span></span> <span data-ttu-id="8dc1e-154">有关搜索条件及通讯簿容器的信息，请参阅 [实现高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-154">For more information about search criteria and address book containers, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>
  
<span data-ttu-id="8dc1e-155">您应支持对搜索结果文件夹中的邮件执行打开、复制、移动和删除操作，而不是对搜索结果文件夹本身执行。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-155">You should support open, copy, move, and delete operations on the messages within search-results folders, not on the search-results folder itself.</span></span> <span data-ttu-id="8dc1e-156">不允许在搜索结果文件夹中创建邮件或将邮件复制到搜索结果文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-156">Do not allow messages to be created within or copied into a search-results folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8dc1e-157">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8dc1e-157">Notes to callers</span></span>

<span data-ttu-id="8dc1e-158">若要搜索邮件收件人，请设置 _lpRestriction_ 以指向子对象限制，将 [SSubRestriction 结构中的 ulSubObject](ssubrestriction.md)成员设置为 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="8dc1e-158">To search for message recipients, set  _lpRestriction_ to point to a subobject restriction with the **ulSubObject** member in the [SSubRestriction](ssubrestriction.md) structure set to **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)).</span></span> <span data-ttu-id="8dc1e-159">若要搜索附件，将 **ulSubObject** 成员设置为PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-159">To search for attachments, set the **ulSubObject** member to **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)).</span></span> <span data-ttu-id="8dc1e-160">将 **lpRes** 成员设置为指向描述收件人或附件的搜索条件的属性限制。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-160">Set the **lpRes** member to point to a property restriction that describes the search criteria for the recipients or attachments.</span></span> 
  
<span data-ttu-id="8dc1e-161">例如，若要查找扩展名为 .mss 的文件附件，将 **ulSubObject** 设置为 **PR_MESSAGE_ATTACHMENTS，** 将 **lpRes** 设置为与 **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) .mss 匹配的属性限制。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-161">For example, to look for file attachments that have the extension .mss, set **ulSubObject** to **PR_MESSAGE_ATTACHMENTS** and **lpRes** to a property restriction that matches **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) with .mss.</span></span>
  
<span data-ttu-id="8dc1e-162">在  _ulSearchFlags_ 参数中设置 FOREGROUND_SEARCH 标志可能会导致系统性能降低。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-162">Setting the FOREGROUND_SEARCH flag in the  _ulSearchFlags_ parameter could cause a decrease in system performance.</span></span> 
  
<span data-ttu-id="8dc1e-163">可以使用 **SetSearchCriteria** 更改已在进行中的搜索的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-163">You can use **SetSearchCriteria** to change the search criteria of a search already in progress.</span></span> <span data-ttu-id="8dc1e-164">您可以指定新的限制、要搜索的文件夹的新列表以及新的搜索优先级，例如将搜索升级到更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-164">You can specify new restrictions, new lists of folders to search, and a new search priority, such as upgrading a search to a higher priority.</span></span> <span data-ttu-id="8dc1e-165">搜索优先级的更改不会导致现有搜索重新启动，但搜索条件的其他更改可能会重新启动。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-165">Changes in search priority do not cause an existing search to restart, but other changes to search criteria can.</span></span> 
  
<span data-ttu-id="8dc1e-166">当您使用搜索结果文件夹时，您可以删除该文件夹或将其保持打开状态，供以后使用。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-166">When you are through using a search-results folder, you can either delete the folder or let it remain open for later use.</span></span> <span data-ttu-id="8dc1e-167">如果删除搜索结果文件夹，则仅删除邮件链接。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-167">If you do delete the search-results folder, only message links are deleted.</span></span> <span data-ttu-id="8dc1e-168">实际邮件仍保留在父文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-168">The actual messages remain in their parent folders.</span></span> 
  
<span data-ttu-id="8dc1e-169">有关搜索结果文件夹详细信息，请参阅 [MAPI 搜索文件夹](mapi-search-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-169">For more information about search-results folders, see [MAPI Search Folders](mapi-search-folders.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="8dc1e-170">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="8dc1e-170">MFCMAPI reference</span></span>

<span data-ttu-id="8dc1e-171">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="8dc1e-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="8dc1e-172">**File**</span></span>|<span data-ttu-id="8dc1e-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="8dc1e-173">**Function**</span></span>|<span data-ttu-id="8dc1e-174">**备注**</span><span class="sxs-lookup"><span data-stu-id="8dc1e-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8dc1e-175">HierarchyTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="8dc1e-175">HierarchyTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="8dc1e-176">CHierarchyTableDlg：：OnEditSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="8dc1e-176">CHierarchyTableDlg::OnEditSearchCriteria</span></span>  <br/> |<span data-ttu-id="8dc1e-177">MFCMAPI 使用 **IMAPIContainer：：SetSearchCriteria** 方法在用户编辑文件夹后为文件夹编写搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8dc1e-177">MFCMAPI uses the **IMAPIContainer::SetSearchCriteria** method to write search criteria for a folder after a user has edited it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8dc1e-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8dc1e-178">See also</span></span>



[<span data-ttu-id="8dc1e-179">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="8dc1e-179">IMAPIContainer::GetContentsTable</span></span>](imapicontainer-getcontentstable.md)
  
[<span data-ttu-id="8dc1e-180">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="8dc1e-180">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
  
[<span data-ttu-id="8dc1e-181">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="8dc1e-181">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
  
[<span data-ttu-id="8dc1e-182">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="8dc1e-182">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="8dc1e-183">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="8dc1e-183">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="8dc1e-184">SRestriction</span><span class="sxs-lookup"><span data-stu-id="8dc1e-184">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="8dc1e-185">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="8dc1e-185">SSubRestriction</span></span>](ssubrestriction.md)
  
[<span data-ttu-id="8dc1e-186">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="8dc1e-186">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="8dc1e-187">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="8dc1e-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

