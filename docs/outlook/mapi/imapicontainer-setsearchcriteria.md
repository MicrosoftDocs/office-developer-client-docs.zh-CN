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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 93578300e2520dda4a9621b05ac6a79c54eca2ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775331"
---
# <a name="imapicontainersetsearchcriteria"></a><span data-ttu-id="9a90f-103">IMAPIContainer::SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="9a90f-103">IMAPIContainer::SetSearchCriteria</span></span>

  
  
<span data-ttu-id="9a90f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9a90f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9a90f-105">建立容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-105">Establishes search criteria for the container.</span></span>
  
```cpp
HRESULT SetSearchCriteria(
  LPSRestriction lpRestriction,
  LPENTRYLIST lpContainerList,
  ULONG ulSearchFlags
);
```

## <a name="parameters"></a><span data-ttu-id="9a90f-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a90f-106">Parameters</span></span>

 <span data-ttu-id="9a90f-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="9a90f-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="9a90f-108">[in]指向定义的搜索条件的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="9a90f-108">[in] A pointer to an [SRestriction](srestriction.md) structure that defines the search criteria.</span></span> <span data-ttu-id="9a90f-109">如果_lpRestriction_参数中传递 NULL，则将再次使用此容器的最近使用的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-109">If NULL is passed in the  _lpRestriction_ parameter, the search criteria that were used most recently for this container are used again.</span></span> <span data-ttu-id="9a90f-110">容器中的第一个搜索中_lpRestriction_应不会传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="9a90f-110">NULL should not be passed in  _lpRestriction_ for the first search in a container.</span></span> 
    
 <span data-ttu-id="9a90f-111">_lpContainerList_</span><span class="sxs-lookup"><span data-stu-id="9a90f-111">_lpContainerList_</span></span>
  
> <span data-ttu-id="9a90f-112">[in]一个指向表示容器要包括在搜索中的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="9a90f-112">[in] A pointer to an array of entry identifiers that represent containers to be included in the search.</span></span> <span data-ttu-id="9a90f-113">如果客户端中_lpContainerList_参数传递 NULL，最近用于搜索此容器的项标识符用于新搜索。</span><span class="sxs-lookup"><span data-stu-id="9a90f-113">If a client passes NULL in the  _lpContainerList_ parameter, the entry identifiers used most recently to search this container are used for the new search.</span></span> <span data-ttu-id="9a90f-114">客户端不应在_lpContainerList_容器中的第一个搜索传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="9a90f-114">A client should not pass NULL in  _lpContainerList_ for the first search in a container.</span></span> 
    
 <span data-ttu-id="9a90f-115">_ulSearchFlags_</span><span class="sxs-lookup"><span data-stu-id="9a90f-115">_ulSearchFlags_</span></span>
  
> <span data-ttu-id="9a90f-116">[in]控制如何执行搜索的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9a90f-116">[in] A bitmask of flags that control how the search is performed.</span></span> <span data-ttu-id="9a90f-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="9a90f-117">The following flags can be set:</span></span>
    
<span data-ttu-id="9a90f-118">BACKGROUND_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-118">BACKGROUND_SEARCH</span></span> 
  
> <span data-ttu-id="9a90f-119">搜索应运行在相对于其他搜索普通优先级。</span><span class="sxs-lookup"><span data-stu-id="9a90f-119">The search should run at normal priority relative to other searches.</span></span> <span data-ttu-id="9a90f-120">不能同时作为 FOREGROUND_SEARCH 标志设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a90f-120">This flag cannot be set at the same time as the FOREGROUND_SEARCH flag.</span></span>
    
<span data-ttu-id="9a90f-121">FOREGROUND_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-121">FOREGROUND_SEARCH</span></span> 
  
> <span data-ttu-id="9a90f-122">搜索应运行在相对于其他搜索高优先级。</span><span class="sxs-lookup"><span data-stu-id="9a90f-122">The search should run at high priority relative to other searches.</span></span> <span data-ttu-id="9a90f-123">不能同时作为 BACKGROUND_SEARCH 标志设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a90f-123">This flag cannot be set at the same time as the BACKGROUND_SEARCH flag.</span></span>
    
<span data-ttu-id="9a90f-124">NON_CONTENT_INDEXED_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-124">NON_CONTENT_INDEXED_SEARCH</span></span>
  
> <span data-ttu-id="9a90f-125">搜索不应使用内容索引来查找匹配项。</span><span class="sxs-lookup"><span data-stu-id="9a90f-125">The search should not use content indexing to find matching entries.</span></span> <span data-ttu-id="9a90f-126">此标志是仅供 Exchange 存储区。</span><span class="sxs-lookup"><span data-stu-id="9a90f-126">This flag is only valid for Exchange stores.</span></span>
    
<span data-ttu-id="9a90f-127">RECURSIVE_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-127">RECURSIVE_SEARCH</span></span> 
  
> <span data-ttu-id="9a90f-128">搜索应包括_lpContainerList_参数及其所有子容器中指定的容器。</span><span class="sxs-lookup"><span data-stu-id="9a90f-128">The search should include the containers specified in the  _lpContainerList_ parameter and all their child containers.</span></span> <span data-ttu-id="9a90f-129">不能同时作为 SHALLOW_SEARCH 标志设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a90f-129">This flag cannot be set at the same time as the SHALLOW_SEARCH flag.</span></span> 
    
<span data-ttu-id="9a90f-130">RESTART_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-130">RESTART_SEARCH</span></span> 
  
> <span data-ttu-id="9a90f-131">搜索应启动如果这是**SetSearchCriteria**，第一个呼叫，或重新启动如果搜索处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="9a90f-131">The search should be initiated if this is the first call to **SetSearchCriteria**, or restarted if the search is inactive.</span></span> <span data-ttu-id="9a90f-132">不能同时作为 STOP_SEARCH 标志设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a90f-132">This flag cannot be set at the same time as the STOP_SEARCH flag.</span></span>
    
<span data-ttu-id="9a90f-133">SHALLOW_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-133">SHALLOW_SEARCH</span></span> 
  
> <span data-ttu-id="9a90f-134">搜索应仅在用于匹配条目_lpContainerList_参数中指定的容器中。</span><span class="sxs-lookup"><span data-stu-id="9a90f-134">The search should look only in the containers specified in the  _lpContainerList_ parameter for matching entries.</span></span> <span data-ttu-id="9a90f-135">不能同时作为 RECURSIVE_SEARCH 标志设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a90f-135">This flag cannot be set at the same time as the RECURSIVE_SEARCH flag.</span></span> 
    
<span data-ttu-id="9a90f-136">STOP_SEARCH</span><span class="sxs-lookup"><span data-stu-id="9a90f-136">STOP_SEARCH</span></span> 
  
> <span data-ttu-id="9a90f-137">应停止搜索。</span><span class="sxs-lookup"><span data-stu-id="9a90f-137">The search should be stopped.</span></span> <span data-ttu-id="9a90f-138">不能同时作为 RESTART_SEARCH 标志设置此标志。</span><span class="sxs-lookup"><span data-stu-id="9a90f-138">This flag cannot be set at the same time as the RESTART_SEARCH flag.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9a90f-139">返回值</span><span class="sxs-lookup"><span data-stu-id="9a90f-139">Return value</span></span>

<span data-ttu-id="9a90f-140">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a90f-140">S_OK</span></span> 
  
> <span data-ttu-id="9a90f-141">已成功设置搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-141">The search criteria was successfully set.</span></span>
    
<span data-ttu-id="9a90f-142">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="9a90f-142">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="9a90f-143">服务提供程序不支持指定的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-143">The service provider does not support the specified search criteria.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9a90f-144">备注</span><span class="sxs-lookup"><span data-stu-id="9a90f-144">Remarks</span></span>

<span data-ttu-id="9a90f-145">**IMAPIContainer::SetSearchCriteria**方法建立支持搜索，通常为一个搜索结果文件夹的容器中的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-145">The **IMAPIContainer::SetSearchCriteria** method establishes search criteria for a container that supports searches, typically a search-results folder.</span></span> <span data-ttu-id="9a90f-146">搜索结果文件夹包含一些主题的链接，符合搜索条件; 的邮件实际邮件仍存储在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="9a90f-146">A search-results folder contains links to the messages that meet the search criteria; the actual messages are still stored in their original locations.</span></span> <span data-ttu-id="9a90f-147">搜索结果文件夹中包含的唯一数据是其内容表。</span><span class="sxs-lookup"><span data-stu-id="9a90f-147">The only unique data that is contained in a search-results folder is its contents table.</span></span> <span data-ttu-id="9a90f-148">内容表中的搜索结果文件夹应用搜索限制后已合并的邮件存储的内容。</span><span class="sxs-lookup"><span data-stu-id="9a90f-148">The contents table of a search-results folder has the merged contents of the message store after the search restriction has been applied.</span></span> 
  
<span data-ttu-id="9a90f-149">搜索操作仅适用于该表合并的内容;它不会通过其他搜索结果文件夹搜索。</span><span class="sxs-lookup"><span data-stu-id="9a90f-149">A search operation works only on this merged contents table; it does not search through other search-results folders.</span></span> <span data-ttu-id="9a90f-150">搜索结果返回符合搜索条件中; 邮件不返回文件夹层次结构。</span><span class="sxs-lookup"><span data-stu-id="9a90f-150">The search results return only the messages that match the search criteria; the folder hierarchy is not returned.</span></span>
  
<span data-ttu-id="9a90f-151">在完成搜索后，将返回到客户端控制权。</span><span class="sxs-lookup"><span data-stu-id="9a90f-151">Control is returned to the client when the search has finished.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="9a90f-152">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="9a90f-152">Notes to implementers</span></span>

<span data-ttu-id="9a90f-153">通讯簿容器通过将限制应用于其内容表中建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-153">Address book containers establish search criteria by applying restrictions to their contents tables.</span></span> <span data-ttu-id="9a90f-154">有关详细信息搜索条件和通讯簿容器，请参阅[实现高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="9a90f-154">For more information about search criteria and address book containers, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>
  
<span data-ttu-id="9a90f-155">应支持 open、 复制、 移动和删除操作对搜索结果文件夹内的邮件，而不对搜索结果文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="9a90f-155">You should support open, copy, move, and delete operations on the messages within search-results folders, not on the search-results folder itself.</span></span> <span data-ttu-id="9a90f-156">不允许邮件中创建或复制到一个搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="9a90f-156">Do not allow messages to be created within or copied into a search-results folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="9a90f-157">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9a90f-157">Notes to callers</span></span>

<span data-ttu-id="9a90f-158">若要搜索的邮件的收件人，设置_lpRestriction_以指向与**ulSubObject**成员[SSubRestriction](ssubrestriction.md)结构设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 中的子对象限制。</span><span class="sxs-lookup"><span data-stu-id="9a90f-158">To search for message recipients, set  _lpRestriction_ to point to a subobject restriction with the **ulSubObject** member in the [SSubRestriction](ssubrestriction.md) structure set to **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)).</span></span> <span data-ttu-id="9a90f-159">若要搜索的附件，将设置为**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 的**ulSubObject**成员。</span><span class="sxs-lookup"><span data-stu-id="9a90f-159">To search for attachments, set the **ulSubObject** member to **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)).</span></span> <span data-ttu-id="9a90f-160">设置要指向的收件人或附件中介绍的搜索标准属性限制的**lpRes**成员。</span><span class="sxs-lookup"><span data-stu-id="9a90f-160">Set the **lpRes** member to point to a property restriction that describes the search criteria for the recipients or attachments.</span></span> 
  
<span data-ttu-id="9a90f-161">例如，要查找具有扩展.mss 的文件附件，设置**ulSubObject** **PR_MESSAGE_ATTACHMENTS**和**lpRes**到匹配**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)属性限制) 与。 mss。</span><span class="sxs-lookup"><span data-stu-id="9a90f-161">For example, to look for file attachments that have the extension .mss, set **ulSubObject** to **PR_MESSAGE_ATTACHMENTS** and **lpRes** to a property restriction that matches **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) with .mss.</span></span>
  
<span data-ttu-id="9a90f-162">设置 FOREGROUND_SEARCH 标志_ulSearchFlags_参数中可能会导致系统性能降低。</span><span class="sxs-lookup"><span data-stu-id="9a90f-162">Setting the FOREGROUND_SEARCH flag in the  _ulSearchFlags_ parameter could cause a decrease in system performance.</span></span> 
  
<span data-ttu-id="9a90f-163">您可以使用**SetSearchCriteria**更改已在进行搜索的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-163">You can use **SetSearchCriteria** to change the search criteria of a search already in progress.</span></span> <span data-ttu-id="9a90f-164">您可以指定新限制、 新列表文件夹搜索和新的搜索优先级，例如将搜索升级到更高的优先级。</span><span class="sxs-lookup"><span data-stu-id="9a90f-164">You can specify new restrictions, new lists of folders to search, and a new search priority, such as upgrading a search to a higher priority.</span></span> <span data-ttu-id="9a90f-165">搜索优先级中的更改不会导致现有搜索要重新启动，但其他更改搜索标准可以。</span><span class="sxs-lookup"><span data-stu-id="9a90f-165">Changes in search priority do not cause an existing search to restart, but other changes to search criteria can.</span></span> 
  
<span data-ttu-id="9a90f-166">当您通过使用的搜索结果文件夹时，可以删除该文件夹或使其保持打开状态以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="9a90f-166">When you are through using a search-results folder, you can either delete the folder or let it remain open for later use.</span></span> <span data-ttu-id="9a90f-167">如果您删除的搜索结果文件夹，将删除仅消息链接。</span><span class="sxs-lookup"><span data-stu-id="9a90f-167">If you do delete the search-results folder, only message links are deleted.</span></span> <span data-ttu-id="9a90f-168">实际的邮件保留在其父文件夹。</span><span class="sxs-lookup"><span data-stu-id="9a90f-168">The actual messages remain in their parent folders.</span></span> 
  
<span data-ttu-id="9a90f-169">有关搜索结果文件夹的详细信息，请参阅[MAPI 搜索文件夹](mapi-search-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="9a90f-169">For more information about search-results folders, see [MAPI Search Folders](mapi-search-folders.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9a90f-170">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="9a90f-170">MFCMAPI reference</span></span>

<span data-ttu-id="9a90f-171">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9a90f-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9a90f-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="9a90f-172">**File**</span></span>|<span data-ttu-id="9a90f-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="9a90f-173">**Function**</span></span>|<span data-ttu-id="9a90f-174">**Comment**</span><span class="sxs-lookup"><span data-stu-id="9a90f-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a90f-175">HierarchyTableDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="9a90f-175">HierarchyTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="9a90f-176">CHierarchyTableDlg::OnEditSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="9a90f-176">CHierarchyTableDlg::OnEditSearchCriteria</span></span>  <br/> |<span data-ttu-id="9a90f-177">MFCMAPI 使用**IMAPIContainer::SetSearchCriteria**方法后用户编辑其文件夹的写入搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9a90f-177">MFCMAPI uses the **IMAPIContainer::SetSearchCriteria** method to write search criteria for a folder after a user has edited it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9a90f-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a90f-178">See also</span></span>



[<span data-ttu-id="9a90f-179">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="9a90f-179">IMAPIContainer::GetContentsTable</span></span>](imapicontainer-getcontentstable.md)
  
[<span data-ttu-id="9a90f-180">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="9a90f-180">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
  
[<span data-ttu-id="9a90f-181">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="9a90f-181">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
  
[<span data-ttu-id="9a90f-182">IMAPIFolder: IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="9a90f-182">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="9a90f-183">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="9a90f-183">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="9a90f-184">SRestriction</span><span class="sxs-lookup"><span data-stu-id="9a90f-184">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="9a90f-185">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="9a90f-185">SSubRestriction</span></span>](ssubrestriction.md)
  
[<span data-ttu-id="9a90f-186">IMAPIContainer: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9a90f-186">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="9a90f-187">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="9a90f-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

