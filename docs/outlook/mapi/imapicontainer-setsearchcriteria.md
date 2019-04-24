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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350965"
---
# <a name="imapicontainersetsearchcriteria"></a><span data-ttu-id="a498b-103">IMAPIContainer::SetSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="a498b-103">IMAPIContainer::SetSearchCriteria</span></span>

  
  
<span data-ttu-id="a498b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a498b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a498b-105">建立容器的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-105">Establishes search criteria for the container.</span></span>
  
```cpp
HRESULT SetSearchCriteria(
  LPSRestriction lpRestriction,
  LPENTRYLIST lpContainerList,
  ULONG ulSearchFlags
);
```

## <a name="parameters"></a><span data-ttu-id="a498b-106">参数</span><span class="sxs-lookup"><span data-stu-id="a498b-106">Parameters</span></span>

 <span data-ttu-id="a498b-107">_lpRestriction_</span><span class="sxs-lookup"><span data-stu-id="a498b-107">_lpRestriction_</span></span>
  
> <span data-ttu-id="a498b-108">实时指向定义搜索条件的[SRestriction](srestriction.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a498b-108">[in] A pointer to an [SRestriction](srestriction.md) structure that defines the search criteria.</span></span> <span data-ttu-id="a498b-109">如果在_lpRestriction_参数中传递 NULL, 则将再次使用此容器最近使用过的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-109">If NULL is passed in the  _lpRestriction_ parameter, the search criteria that were used most recently for this container are used again.</span></span> <span data-ttu-id="a498b-110">对于容器中的第一个搜索, 不应在_lpRestriction_中传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="a498b-110">NULL should not be passed in  _lpRestriction_ for the first search in a container.</span></span> 
    
 <span data-ttu-id="a498b-111">_lpContainerList_</span><span class="sxs-lookup"><span data-stu-id="a498b-111">_lpContainerList_</span></span>
  
> <span data-ttu-id="a498b-112">实时指向表示要包括在搜索中的容器的条目标识符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a498b-112">[in] A pointer to an array of entry identifiers that represent containers to be included in the search.</span></span> <span data-ttu-id="a498b-113">如果客户端在_lpContainerList_参数中传递了 NULL, 则最近使用的搜索此容器的条目标识符将用于新的搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-113">If a client passes NULL in the  _lpContainerList_ parameter, the entry identifiers used most recently to search this container are used for the new search.</span></span> <span data-ttu-id="a498b-114">客户端不应在_lpContainerList_中传递 NULL 以查找容器中的第一次搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-114">A client should not pass NULL in  _lpContainerList_ for the first search in a container.</span></span> 
    
 <span data-ttu-id="a498b-115">_ulSearchFlags_</span><span class="sxs-lookup"><span data-stu-id="a498b-115">_ulSearchFlags_</span></span>
  
> <span data-ttu-id="a498b-116">实时用于控制如何执行搜索的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a498b-116">[in] A bitmask of flags that control how the search is performed.</span></span> <span data-ttu-id="a498b-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a498b-117">The following flags can be set:</span></span>
    
<span data-ttu-id="a498b-118">BACKGROUND_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-118">BACKGROUND_SEARCH</span></span> 
  
> <span data-ttu-id="a498b-119">搜索应以常规优先级运行, 相对于其他搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-119">The search should run at normal priority relative to other searches.</span></span> <span data-ttu-id="a498b-120">此标志不能与 FOREGROUND_SEARCH 标志同时设置。</span><span class="sxs-lookup"><span data-stu-id="a498b-120">This flag cannot be set at the same time as the FOREGROUND_SEARCH flag.</span></span>
    
<span data-ttu-id="a498b-121">FOREGROUND_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-121">FOREGROUND_SEARCH</span></span> 
  
> <span data-ttu-id="a498b-122">搜索应以高优先级运行, 相对于其他搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-122">The search should run at high priority relative to other searches.</span></span> <span data-ttu-id="a498b-123">此标志不能与 BACKGROUND_SEARCH 标志同时设置。</span><span class="sxs-lookup"><span data-stu-id="a498b-123">This flag cannot be set at the same time as the BACKGROUND_SEARCH flag.</span></span>
    
<span data-ttu-id="a498b-124">NON_CONTENT_INDEXED_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-124">NON_CONTENT_INDEXED_SEARCH</span></span>
  
> <span data-ttu-id="a498b-125">搜索不应使用内容索引来查找匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="a498b-125">The search should not use content indexing to find matching entries.</span></span> <span data-ttu-id="a498b-126">此标志仅对 Exchange 存储有效。</span><span class="sxs-lookup"><span data-stu-id="a498b-126">This flag is only valid for Exchange stores.</span></span>
    
<span data-ttu-id="a498b-127">RECURSIVE_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-127">RECURSIVE_SEARCH</span></span> 
  
> <span data-ttu-id="a498b-128">搜索应包括_lpContainerList_参数中指定的容器及其所有子容器。</span><span class="sxs-lookup"><span data-stu-id="a498b-128">The search should include the containers specified in the  _lpContainerList_ parameter and all their child containers.</span></span> <span data-ttu-id="a498b-129">此标志不能与 SHALLOW_SEARCH 标志同时设置。</span><span class="sxs-lookup"><span data-stu-id="a498b-129">This flag cannot be set at the same time as the SHALLOW_SEARCH flag.</span></span> 
    
<span data-ttu-id="a498b-130">RESTART_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-130">RESTART_SEARCH</span></span> 
  
> <span data-ttu-id="a498b-131">如果这是第一次调用**SetSearchCriteria**, 则应启动搜索, 如果搜索处于非活动状态, 则会重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-131">The search should be initiated if this is the first call to **SetSearchCriteria**, or restarted if the search is inactive.</span></span> <span data-ttu-id="a498b-132">此标志不能与 STOP_SEARCH 标志同时设置。</span><span class="sxs-lookup"><span data-stu-id="a498b-132">This flag cannot be set at the same time as the STOP_SEARCH flag.</span></span>
    
<span data-ttu-id="a498b-133">SHALLOW_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-133">SHALLOW_SEARCH</span></span> 
  
> <span data-ttu-id="a498b-134">搜索应仅在_lpContainerList_参数中指定的容器中查找匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="a498b-134">The search should look only in the containers specified in the  _lpContainerList_ parameter for matching entries.</span></span> <span data-ttu-id="a498b-135">此标志不能与 RECURSIVE_SEARCH 标志同时设置。</span><span class="sxs-lookup"><span data-stu-id="a498b-135">This flag cannot be set at the same time as the RECURSIVE_SEARCH flag.</span></span> 
    
<span data-ttu-id="a498b-136">STOP_SEARCH</span><span class="sxs-lookup"><span data-stu-id="a498b-136">STOP_SEARCH</span></span> 
  
> <span data-ttu-id="a498b-137">应停止搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-137">The search should be stopped.</span></span> <span data-ttu-id="a498b-138">此标志不能与 RESTART_SEARCH 标志同时设置。</span><span class="sxs-lookup"><span data-stu-id="a498b-138">This flag cannot be set at the same time as the RESTART_SEARCH flag.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a498b-139">返回值</span><span class="sxs-lookup"><span data-stu-id="a498b-139">Return value</span></span>

<span data-ttu-id="a498b-140">S_OK</span><span class="sxs-lookup"><span data-stu-id="a498b-140">S_OK</span></span> 
  
> <span data-ttu-id="a498b-141">已成功设置搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-141">The search criteria was successfully set.</span></span>
    
<span data-ttu-id="a498b-142">MAPI_E_TOO_COMPLEX</span><span class="sxs-lookup"><span data-stu-id="a498b-142">MAPI_E_TOO_COMPLEX</span></span> 
  
> <span data-ttu-id="a498b-143">服务提供商不支持指定的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-143">The service provider does not support the specified search criteria.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a498b-144">注解</span><span class="sxs-lookup"><span data-stu-id="a498b-144">Remarks</span></span>

<span data-ttu-id="a498b-145">**IMAPIContainer:: SetSearchCriteria**方法为支持搜索的容器 (通常为搜索结果文件夹) 建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-145">The **IMAPIContainer::SetSearchCriteria** method establishes search criteria for a container that supports searches, typically a search-results folder.</span></span> <span data-ttu-id="a498b-146">搜索结果文件夹包含符合搜索条件的邮件的链接;实际邮件仍存储在其原始位置。</span><span class="sxs-lookup"><span data-stu-id="a498b-146">A search-results folder contains links to the messages that meet the search criteria; the actual messages are still stored in their original locations.</span></span> <span data-ttu-id="a498b-147">搜索结果文件夹中唯一包含的唯一数据是其内容表格。</span><span class="sxs-lookup"><span data-stu-id="a498b-147">The only unique data that is contained in a search-results folder is its contents table.</span></span> <span data-ttu-id="a498b-148">在应用搜索限制后, 搜索结果文件夹的 "内容" 表格具有邮件存储的合并内容。</span><span class="sxs-lookup"><span data-stu-id="a498b-148">The contents table of a search-results folder has the merged contents of the message store after the search restriction has been applied.</span></span> 
  
<span data-ttu-id="a498b-149">搜索操作仅适用于此合并内容表格;它不会在其他搜索结果文件夹中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="a498b-149">A search operation works only on this merged contents table; it does not search through other search-results folders.</span></span> <span data-ttu-id="a498b-150">搜索结果仅返回与搜索条件匹配的邮件;不返回文件夹层次结构。</span><span class="sxs-lookup"><span data-stu-id="a498b-150">The search results return only the messages that match the search criteria; the folder hierarchy is not returned.</span></span>
  
<span data-ttu-id="a498b-151">搜索完成后, 控件将返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="a498b-151">Control is returned to the client when the search has finished.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="a498b-152">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="a498b-152">Notes to implementers</span></span>

<span data-ttu-id="a498b-153">通讯簿容器通过对其内容表应用限制来建立搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-153">Address book containers establish search criteria by applying restrictions to their contents tables.</span></span> <span data-ttu-id="a498b-154">有关搜索条件和通讯簿容器的详细信息, 请参阅[实施高级搜索](implementing-advanced-searching.md)。</span><span class="sxs-lookup"><span data-stu-id="a498b-154">For more information about search criteria and address book containers, see [Implementing Advanced Searching](implementing-advanced-searching.md).</span></span>
  
<span data-ttu-id="a498b-155">您应支持对搜索结果文件夹中的邮件进行打开、复制、移动和删除操作, 而不是搜索结果文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="a498b-155">You should support open, copy, move, and delete operations on the messages within search-results folders, not on the search-results folder itself.</span></span> <span data-ttu-id="a498b-156">不允许在搜索结果文件夹中创建邮件或将邮件复制到搜索结果文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a498b-156">Do not allow messages to be created within or copied into a search-results folder.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a498b-157">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a498b-157">Notes to callers</span></span>

<span data-ttu-id="a498b-158">若要搜索邮件收件人, 请将_lpRestriction_设置为指向一个子范围限制, 并将[SSubRestriction](ssubrestriction.md)结构中的**ulSubObject**成员设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="a498b-158">To search for message recipients, set  _lpRestriction_ to point to a subobject restriction with the **ulSubObject** member in the [SSubRestriction](ssubrestriction.md) structure set to **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)).</span></span> <span data-ttu-id="a498b-159">若要搜索附件, 请将**ulSubObject**成员设置为**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="a498b-159">To search for attachments, set the **ulSubObject** member to **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)).</span></span> <span data-ttu-id="a498b-160">将**lpRes**成员设置为指向描述收件人或附件的搜索条件的属性限制。</span><span class="sxs-lookup"><span data-stu-id="a498b-160">Set the **lpRes** member to point to a property restriction that describes the search criteria for the recipients or attachments.</span></span> 
  
<span data-ttu-id="a498b-161">例如, 若要查找扩展名为 mss 的文件附件, 请将**ulSubObject**设置为**PR_MESSAGE_ATTACHMENTS** , 并将**lpRes**设置为匹配**PR_ATTACH_EXTENSION**的属性限制 ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) (mss)。</span><span class="sxs-lookup"><span data-stu-id="a498b-161">For example, to look for file attachments that have the extension .mss, set **ulSubObject** to **PR_MESSAGE_ATTACHMENTS** and **lpRes** to a property restriction that matches **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) with .mss.</span></span>
  
<span data-ttu-id="a498b-162">在_ulSearchFlags_参数中设置 FOREGROUND_SEARCH 标志可能会导致系统性能降低。</span><span class="sxs-lookup"><span data-stu-id="a498b-162">Setting the FOREGROUND_SEARCH flag in the  _ulSearchFlags_ parameter could cause a decrease in system performance.</span></span> 
  
<span data-ttu-id="a498b-163">您可以使用**SetSearchCriteria**更改已在进行的搜索的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-163">You can use **SetSearchCriteria** to change the search criteria of a search already in progress.</span></span> <span data-ttu-id="a498b-164">您可以指定新的限制、要搜索的文件夹的新列表以及新的搜索优先级 (例如将搜索升级为较高的优先级)。</span><span class="sxs-lookup"><span data-stu-id="a498b-164">You can specify new restrictions, new lists of folders to search, and a new search priority, such as upgrading a search to a higher priority.</span></span> <span data-ttu-id="a498b-165">搜索优先级中的更改不会导致现有搜索重新启动, 但可以对搜索条件进行其他更改。</span><span class="sxs-lookup"><span data-stu-id="a498b-165">Changes in search priority do not cause an existing search to restart, but other changes to search criteria can.</span></span> 
  
<span data-ttu-id="a498b-166">当您使用搜索结果文件夹时, 您可以删除该文件夹或让其保持打开状态以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="a498b-166">When you are through using a search-results folder, you can either delete the folder or let it remain open for later use.</span></span> <span data-ttu-id="a498b-167">如果确实删除搜索结果文件夹, 则只会删除邮件链接。</span><span class="sxs-lookup"><span data-stu-id="a498b-167">If you do delete the search-results folder, only message links are deleted.</span></span> <span data-ttu-id="a498b-168">实际邮件仍保留在其父文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a498b-168">The actual messages remain in their parent folders.</span></span> 
  
<span data-ttu-id="a498b-169">有关搜索结果文件夹的详细信息, 请参阅[MAPI 搜索文件夹](mapi-search-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="a498b-169">For more information about search-results folders, see [MAPI Search Folders](mapi-search-folders.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a498b-170">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a498b-170">MFCMAPI reference</span></span>

<span data-ttu-id="a498b-171">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a498b-171">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a498b-172">**文件**</span><span class="sxs-lookup"><span data-stu-id="a498b-172">**File**</span></span>|<span data-ttu-id="a498b-173">**函数**</span><span class="sxs-lookup"><span data-stu-id="a498b-173">**Function**</span></span>|<span data-ttu-id="a498b-174">**备注**</span><span class="sxs-lookup"><span data-stu-id="a498b-174">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a498b-175">HierarchyTableDlg</span><span class="sxs-lookup"><span data-stu-id="a498b-175">HierarchyTableDlg.cpp</span></span>  <br/> |<span data-ttu-id="a498b-176">CHierarchyTableDlg:: OnEditSearchCriteria</span><span class="sxs-lookup"><span data-stu-id="a498b-176">CHierarchyTableDlg::OnEditSearchCriteria</span></span>  <br/> |<span data-ttu-id="a498b-177">MFCMAPI 使用**IMAPIContainer:: SetSearchCriteria**方法在用户对文件夹进行编辑之后为该文件夹编写搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a498b-177">MFCMAPI uses the **IMAPIContainer::SetSearchCriteria** method to write search criteria for a folder after a user has edited it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a498b-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a498b-178">See also</span></span>



[<span data-ttu-id="a498b-179">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="a498b-179">IMAPIContainer::GetContentsTable</span></span>](imapicontainer-getcontentstable.md)
  
[<span data-ttu-id="a498b-180">IMAPIContainer::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a498b-180">IMAPIContainer::OpenEntry</span></span>](imapicontainer-openentry.md)
  
[<span data-ttu-id="a498b-181">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="a498b-181">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
  
[<span data-ttu-id="a498b-182">IMAPIFolder : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="a498b-182">IMAPIFolder : IMAPIContainer</span></span>](imapifolderimapicontainer.md)
  
[<span data-ttu-id="a498b-183">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="a498b-183">SPropertyRestriction</span></span>](spropertyrestriction.md)
  
[<span data-ttu-id="a498b-184">SRestriction</span><span class="sxs-lookup"><span data-stu-id="a498b-184">SRestriction</span></span>](srestriction.md)
  
[<span data-ttu-id="a498b-185">SSubRestriction</span><span class="sxs-lookup"><span data-stu-id="a498b-185">SSubRestriction</span></span>](ssubrestriction.md)
  
[<span data-ttu-id="a498b-186">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="a498b-186">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="a498b-187">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a498b-187">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

