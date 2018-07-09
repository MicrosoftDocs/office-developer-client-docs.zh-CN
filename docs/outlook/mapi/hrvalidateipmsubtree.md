---
title: HrValidateIPMSubtree
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrValidateIPMSubtree
api_type:
- COM
ms.assetid: 6454c1fa-5216-4934-a908-48c634ac4a07
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8b6d4fa1d9ffa6ab5f800bad9f02ac5aa9abd8c0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775188"
---
# <a name="hrvalidateipmsubtree"></a><span data-ttu-id="3e86b-103">HrValidateIPMSubtree</span><span class="sxs-lookup"><span data-stu-id="3e86b-103">HrValidateIPMSubtree</span></span>

  
  
<span data-ttu-id="3e86b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e86b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e86b-105">将标准人际邮件 (IPM) 文件夹添加到的消息存储。</span><span class="sxs-lookup"><span data-stu-id="3e86b-105">Adds standard interpersonal message (IPM) folders to a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3e86b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3e86b-106">Header file:</span></span>  <br/> |<span data-ttu-id="3e86b-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="3e86b-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3e86b-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="3e86b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3e86b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3e86b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3e86b-110">调用：</span><span class="sxs-lookup"><span data-stu-id="3e86b-110">Called by:</span></span>  <br/> |<span data-ttu-id="3e86b-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="3e86b-111">Client applications</span></span>  <br/> |
   
```cpp
HrValidateIPMSubtree(
  LPMDB lpMDB,
  ULONG ulFlags,
  ULONG FAR * lpcValues,
  LPSPropValue FAR * lppProps,
  LPMAPIERROR FAR * lppMapiError
);
```

## <a name="parameters"></a><span data-ttu-id="3e86b-112">参数</span><span class="sxs-lookup"><span data-stu-id="3e86b-112">Parameters</span></span>

 <span data-ttu-id="3e86b-113">_lpMDB_</span><span class="sxs-lookup"><span data-stu-id="3e86b-113">_lpMDB_</span></span>
  
> <span data-ttu-id="3e86b-114">[in]指向邮件存储要向其中添加文件夹的对象。</span><span class="sxs-lookup"><span data-stu-id="3e86b-114">[in] Pointer to the message store object to which to add the folders.</span></span> 
    
 <span data-ttu-id="3e86b-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3e86b-115">_ulFlags_</span></span>
  
> <span data-ttu-id="3e86b-116">[in]用于控制如何创建的文件夹的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="3e86b-116">[in] Bitmask of flags used to control how the folders are created.</span></span> <span data-ttu-id="3e86b-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="3e86b-117">The following flags can be set:</span></span>
    
<span data-ttu-id="3e86b-118">MAPI_FORCE_CREATE</span><span class="sxs-lookup"><span data-stu-id="3e86b-118">MAPI_FORCE_CREATE</span></span> 
  
> <span data-ttu-id="3e86b-119">之前创建，应验证文件夹，即使它们是有效的消息存储库属性指示。</span><span class="sxs-lookup"><span data-stu-id="3e86b-119">The folders should be verified before creation, even if message store properties indicate that they are valid.</span></span> <span data-ttu-id="3e86b-120">一个错误，指示已损坏的现有文件夹结构时，客户端应用程序通常设置此标志。</span><span class="sxs-lookup"><span data-stu-id="3e86b-120">A client application typically sets this flag when an error indicates that the structure of an existing folder has been damaged.</span></span> 
    
<span data-ttu-id="3e86b-121">MAPI_FULL_IPM_TREE</span><span class="sxs-lookup"><span data-stu-id="3e86b-121">MAPI_FULL_IPM_TREE</span></span> 
  
> <span data-ttu-id="3e86b-122">消息存储库的根文件夹中，应创建整套 IPM 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e86b-122">The full set of IPM folders should be created in the message store's root folder.</span></span> <span data-ttu-id="3e86b-123">层次结构中的文件夹标题是：</span><span class="sxs-lookup"><span data-stu-id="3e86b-123">The folder titles in the hierarchy are:</span></span>
    
    - <span data-ttu-id="3e86b-124">文件夹视图</span><span class="sxs-lookup"><span data-stu-id="3e86b-124">Folder Views</span></span>
    
    - <span data-ttu-id="3e86b-125">公共视图</span><span class="sxs-lookup"><span data-stu-id="3e86b-125">Common Views</span></span>
    
    - <span data-ttu-id="3e86b-126">搜索根\*</span><span class="sxs-lookup"><span data-stu-id="3e86b-126">Search Root\*</span></span>
    
    - <span data-ttu-id="3e86b-127">IPM 子树\*</span><span class="sxs-lookup"><span data-stu-id="3e86b-127">IPM Subtree\*</span></span>
    
    - <span data-ttu-id="3e86b-128">Inbox</span><span class="sxs-lookup"><span data-stu-id="3e86b-128">Inbox</span></span>
    
    - <span data-ttu-id="3e86b-129">发件箱</span><span class="sxs-lookup"><span data-stu-id="3e86b-129">Outbox</span></span>
    
    - <span data-ttu-id="3e86b-130">已删除的项目\*</span><span class="sxs-lookup"><span data-stu-id="3e86b-130">Deleted Items\*</span></span>
    
    - <span data-ttu-id="3e86b-131">已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="3e86b-131">Sent Items</span></span>
    
    <span data-ttu-id="3e86b-132">三个文件夹与标记的位置\*是最小集创建即使 MAPI_FULL_IPM_TREE 标志尚未设置。</span><span class="sxs-lookup"><span data-stu-id="3e86b-132">where the three folders marked with \* are the minimum set created even when the MAPI_FULL_IPM_TREE flag has not been set.</span></span> <span data-ttu-id="3e86b-133">客户端应用程序通常将在其中的文件夹是要创建的消息存储时的默认存储设置此标志。</span><span class="sxs-lookup"><span data-stu-id="3e86b-133">A client application typically sets this flag when the message store in which the folders are to be created is the default store.</span></span>
    
 <span data-ttu-id="3e86b-134">_lpcValues_</span><span class="sxs-lookup"><span data-stu-id="3e86b-134">_lpcValues_</span></span>
  
> <span data-ttu-id="3e86b-135">[传入、 传出]指向[SPropValue](spropvalue.md)结构_lppProps_参数中返回的数组中的编号的指针。</span><span class="sxs-lookup"><span data-stu-id="3e86b-135">[in, out] Pointer to the number of [SPropValue](spropvalue.md) structures in the array returned in the  _lppProps_ parameter.</span></span> <span data-ttu-id="3e86b-136">_LpcValues_参数的值可以是零，如果_lppProps_为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e86b-136">The value of the  _lpcValues_ parameter can be zero if  _lppProps_ is NULL.</span></span> 
    
 <span data-ttu-id="3e86b-137">_lppProps_</span><span class="sxs-lookup"><span data-stu-id="3e86b-137">_lppProps_</span></span>
  
> <span data-ttu-id="3e86b-138">[传入、 传出]为指向包含属性值为**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性以及相应的文件夹条目标识符属性的**SPropValue**结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="3e86b-138">[in, out] Pointer to a pointer to an array of **SPropValue** structures that contains property values for the **PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) property and for the appropriate folder entry identifier properties.</span></span> <span data-ttu-id="3e86b-139">如果**HrValidateIPMSubtree**消息存储库中创建收件箱， **SPropValue**数组包括收件箱条目标识符，其中编码为一个特殊属性标记`PROP_TAG(PT_BINARY, PROP_ID_NULL)`。</span><span class="sxs-lookup"><span data-stu-id="3e86b-139">If **HrValidateIPMSubtree** creates an Inbox in the message store, the **SPropValue** array includes an Inbox entry identifier with a special property tag coded as  `PROP_TAG(PT_BINARY, PROP_ID_NULL)`.</span></span> <span data-ttu-id="3e86b-140">_LppProps_参数可以是 NULL，表明调用实现不需要返回**SPropValue**数组。</span><span class="sxs-lookup"><span data-stu-id="3e86b-140">The  _lppProps_ parameter can be NULL, indicating that the calling implementation does not require that an **SPropValue** array be returned.</span></span> 
    
 <span data-ttu-id="3e86b-141">_lppMapiError_</span><span class="sxs-lookup"><span data-stu-id="3e86b-141">_lppMapiError_</span></span>
  
> <span data-ttu-id="3e86b-142">[输出]为包含错误的版本、 组件及上下文信息[MAPIERROR](mapierror.md)结构指针的指针。</span><span class="sxs-lookup"><span data-stu-id="3e86b-142">[out] Pointer to a pointer to a [MAPIERROR](mapierror.md) structure that contains version, component, and context information for an error.</span></span> <span data-ttu-id="3e86b-143">如果不返回任何**MAPIERROR**结构_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3e86b-143">The  _lppMAPIError_ parameter is set to NULL if no **MAPIERROR** structure is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3e86b-144">返回值</span><span class="sxs-lookup"><span data-stu-id="3e86b-144">Return value</span></span>

<span data-ttu-id="3e86b-145">无。</span><span class="sxs-lookup"><span data-stu-id="3e86b-145">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3e86b-146">备注</span><span class="sxs-lookup"><span data-stu-id="3e86b-146">Remarks</span></span>

<span data-ttu-id="3e86b-147">MAPI 内部使用**HrValidateIPMSubtree**函数来构造中的消息存储的标准 IPM 子树时首先打开的存储，或者存储区进行的默认存储。</span><span class="sxs-lookup"><span data-stu-id="3e86b-147">MAPI uses the **HrValidateIPMSubtree** function internally to construct the standard IPM subtree in a message store when the store is first opened, or when a store is made the default store.</span></span> <span data-ttu-id="3e86b-148">此函数还可通过客户端应用程序以验证或修复标准邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e86b-148">This function can also be used by client applications to validate or repair standard message folders.</span></span> 
  
 <span data-ttu-id="3e86b-149">**HrValidateIPMSubtree**始终存储的根文件夹和 IPM 子树文件夹中的已删除邮件文件夹中创建的搜索根和 IPM 子树文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e86b-149">**HrValidateIPMSubtree** always creates the Search Root and IPM Subtree folders in the store's root folder and the Deleted Items folder in the IPM Subtree folder.</span></span> <span data-ttu-id="3e86b-150">IPM 子树的文件夹是该消息存储中 IPM 层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="3e86b-150">The IPM Subtree folder is the root of the IPM hierarchy in that message store.</span></span> <span data-ttu-id="3e86b-151">搜索根文件夹可以用作搜索结果文件夹的子树的根。</span><span class="sxs-lookup"><span data-stu-id="3e86b-151">The Search Root folder can be used as the root of a subtree for search-results folders.</span></span> 
  
<span data-ttu-id="3e86b-152">IPM 客户端应该显示开头 IPM 子树的根文件夹和显示在它下面的文件夹的子其文件夹视图。</span><span class="sxs-lookup"><span data-stu-id="3e86b-152">IPM clients should display their folder view starting at the IPM subtree root folder and showing child folders beneath it.</span></span> <span data-ttu-id="3e86b-153">在客户端的用户界面中不应出现的消息存储的根文件夹中的信息。</span><span class="sxs-lookup"><span data-stu-id="3e86b-153">Information in the root folder of a message store should not appear in a client's user interface.</span></span> <span data-ttu-id="3e86b-154">此功能意味着，如果客户端必须隐藏信息，请信息可以放置在 IPM 子树的根目录，其中不对用户可见。</span><span class="sxs-lookup"><span data-stu-id="3e86b-154">This functionality means that if a client must hide information, the information can be put in the IPM subtree root directory, where it is not visible to the user.</span></span> <span data-ttu-id="3e86b-155">相比之下，需要邮件和文件夹，使其与用户，例如基于服务器的邮件存储区中，不可见的非 IPM 应用程序可以将它们放外 IPM 层次结构。</span><span class="sxs-lookup"><span data-stu-id="3e86b-155">In contrast, non-IPM applications that require messages and folders to be invisible to the user, for example in a server-based message store, can put them outside the IPM hierarchy.</span></span> 
  
 <span data-ttu-id="3e86b-156">**HrValidateIPMSubtree**设置**PR_VALID_FOLDER_MASK**属性，以指示它创建每个 IPM 文件夹是否具有有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="3e86b-156">**HrValidateIPMSubtree** sets the **PR_VALID_FOLDER_MASK** property to indicate whether each IPM folder it creates has a valid entry identifier.</span></span> <span data-ttu-id="3e86b-157">消息存储库的下列条目标识符属性设置为相应的文件夹中的项标识符，以及**PR_VALID_FOLDER_MASK** _lppProps_参数中返回：</span><span class="sxs-lookup"><span data-stu-id="3e86b-157">The following entry identifier properties of the message store are set to the entry identifiers of the corresponding folders and returned in the  _lppProps_ parameter along with **PR_VALID_FOLDER_MASK**:</span></span> 
  
 <span data-ttu-id="3e86b-158">**PR_COMMON_VIEWS_ENTRYID**([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-158">**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-159">**PR_FINDER_ENTRYID**([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-159">**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-160">**PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-160">**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-161">**PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-161">**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-162">**PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-162">**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-163">**PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-163">**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-164">**PR_VIEWS_ENTRYID**([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="3e86b-164">**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="3e86b-165">占位符[PROP_TAG](prop_tag.md) IPM 收件箱 （PT_BINARY、 PROP_ID_NULL）。</span><span class="sxs-lookup"><span data-stu-id="3e86b-165">A placeholder [PROP_TAG](prop_tag.md) for the IPM Inbox (PT_BINARY, PROP_ID_NULL).</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="3e86b-166">MFCMAPI 参考</span><span class="sxs-lookup"><span data-stu-id="3e86b-166">MFCMAPI reference</span></span>

<span data-ttu-id="3e86b-167">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3e86b-167">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3e86b-168">**文件**</span><span class="sxs-lookup"><span data-stu-id="3e86b-168">**File**</span></span>|<span data-ttu-id="3e86b-169">**函数**</span><span class="sxs-lookup"><span data-stu-id="3e86b-169">**Function**</span></span>|<span data-ttu-id="3e86b-170">**Comment**</span><span class="sxs-lookup"><span data-stu-id="3e86b-170">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e86b-171">MstStoreDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="3e86b-171">MstStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="3e86b-172">CMsgStoreDlg::OnValidateIPMSubtree</span><span class="sxs-lookup"><span data-stu-id="3e86b-172">CMsgStoreDlg::OnValidateIPMSubtree</span></span>  <br/> |<span data-ttu-id="3e86b-173">MFCMAPI 使用**HrValidateIPMSubtree**方法将标准文件夹添加到的消息存储。</span><span class="sxs-lookup"><span data-stu-id="3e86b-173">MFCMAPI uses the **HrValidateIPMSubtree** method to add standard folders to a message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3e86b-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e86b-174">See also</span></span>



[<span data-ttu-id="3e86b-175">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="3e86b-175">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)


[<span data-ttu-id="3e86b-176">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="3e86b-176">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

