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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cf51985e534434c584eff4d63dfbf239121ee85
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436571"
---
# <a name="hrvalidateipmsubtree"></a><span data-ttu-id="a7757-103">HrValidateIPMSubtree</span><span class="sxs-lookup"><span data-stu-id="a7757-103">HrValidateIPMSubtree</span></span>

  
  
<span data-ttu-id="a7757-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7757-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7757-105">将标准人际邮件 (IPM) 文件夹添加到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="a7757-105">Adds standard interpersonal message (IPM) folders to a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a7757-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a7757-106">Header file:</span></span>  <br/> |<span data-ttu-id="a7757-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="a7757-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a7757-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a7757-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a7757-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a7757-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a7757-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a7757-110">Called by:</span></span>  <br/> |<span data-ttu-id="a7757-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="a7757-111">Client applications</span></span>  <br/> |
   
```cpp
HrValidateIPMSubtree(
  LPMDB lpMDB,
  ULONG ulFlags,
  ULONG FAR * lpcValues,
  LPSPropValue FAR * lppProps,
  LPMAPIERROR FAR * lppMapiError
);
```

## <a name="parameters"></a><span data-ttu-id="a7757-112">参数</span><span class="sxs-lookup"><span data-stu-id="a7757-112">Parameters</span></span>

 <span data-ttu-id="a7757-113">_lpMDB_</span><span class="sxs-lookup"><span data-stu-id="a7757-113">_lpMDB_</span></span>
  
> <span data-ttu-id="a7757-114">实时指向要向其添加文件夹的邮件存储对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a7757-114">[in] Pointer to the message store object to which to add the folders.</span></span> 
    
 <span data-ttu-id="a7757-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a7757-115">_ulFlags_</span></span>
  
> <span data-ttu-id="a7757-116">实时用于控制创建文件夹的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a7757-116">[in] Bitmask of flags used to control how the folders are created.</span></span> <span data-ttu-id="a7757-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a7757-117">The following flags can be set:</span></span>
    
<span data-ttu-id="a7757-118">MAPI_FORCE_CREATE</span><span class="sxs-lookup"><span data-stu-id="a7757-118">MAPI_FORCE_CREATE</span></span> 
  
> <span data-ttu-id="a7757-119">应在创建文件夹之前对其进行验证, 即使邮件存储库属性指示它们是有效的也是如此。</span><span class="sxs-lookup"><span data-stu-id="a7757-119">The folders should be verified before creation, even if message store properties indicate that they are valid.</span></span> <span data-ttu-id="a7757-120">当错误指示现有文件夹的结构已损坏时, 客户端应用程序通常会设置此标志。</span><span class="sxs-lookup"><span data-stu-id="a7757-120">A client application typically sets this flag when an error indicates that the structure of an existing folder has been damaged.</span></span> 
    
<span data-ttu-id="a7757-121">MAPI_FULL_IPM_TREE</span><span class="sxs-lookup"><span data-stu-id="a7757-121">MAPI_FULL_IPM_TREE</span></span> 
  
> <span data-ttu-id="a7757-122">应在邮件存储区的根文件夹中创建完整的 IPM 文件夹集。</span><span class="sxs-lookup"><span data-stu-id="a7757-122">The full set of IPM folders should be created in the message store's root folder.</span></span> <span data-ttu-id="a7757-123">层次结构中的文件夹标题为:</span><span class="sxs-lookup"><span data-stu-id="a7757-123">The folder titles in the hierarchy are:</span></span>
    
    - <span data-ttu-id="a7757-124">文件夹视图</span><span class="sxs-lookup"><span data-stu-id="a7757-124">Folder Views</span></span>
    
    - <span data-ttu-id="a7757-125">常用视图</span><span class="sxs-lookup"><span data-stu-id="a7757-125">Common Views</span></span>
    
    - <span data-ttu-id="a7757-126">搜索根\*</span><span class="sxs-lookup"><span data-stu-id="a7757-126">Search Root\*</span></span>
    
    - <span data-ttu-id="a7757-127">IPM 子树\*</span><span class="sxs-lookup"><span data-stu-id="a7757-127">IPM Subtree\*</span></span>
    
    - <span data-ttu-id="a7757-128">Inbox</span><span class="sxs-lookup"><span data-stu-id="a7757-128">Inbox</span></span>
    
    - <span data-ttu-id="a7757-129">发件箱</span><span class="sxs-lookup"><span data-stu-id="a7757-129">Outbox</span></span>
    
    - <span data-ttu-id="a7757-130">已删除项目\*</span><span class="sxs-lookup"><span data-stu-id="a7757-130">Deleted Items\*</span></span>
    
    - <span data-ttu-id="a7757-131">已发送邮件</span><span class="sxs-lookup"><span data-stu-id="a7757-131">Sent Items</span></span>
    
    <span data-ttu-id="a7757-132">其中, 使用\*标记的三个文件夹是创建的最小集, 即使尚未设置 MAPI_FULL_IPM_TREE 标志也是如此。</span><span class="sxs-lookup"><span data-stu-id="a7757-132">where the three folders marked with \* are the minimum set created even when the MAPI_FULL_IPM_TREE flag has not been set.</span></span> <span data-ttu-id="a7757-133">当要在其中创建文件夹的邮件存储是默认存储时, 客户端应用程序通常会设置此标志。</span><span class="sxs-lookup"><span data-stu-id="a7757-133">A client application typically sets this flag when the message store in which the folders are to be created is the default store.</span></span>
    
 <span data-ttu-id="a7757-134">_lpcValues_</span><span class="sxs-lookup"><span data-stu-id="a7757-134">_lpcValues_</span></span>
  
> <span data-ttu-id="a7757-135">[in, out]一个指针, 指向_lppProps_参数中返回的数组中的[SPropValue](spropvalue.md)结构的数目。</span><span class="sxs-lookup"><span data-stu-id="a7757-135">[in, out] Pointer to the number of [SPropValue](spropvalue.md) structures in the array returned in the  _lppProps_ parameter.</span></span> <span data-ttu-id="a7757-136">如果_lppProps_为 NULL, 则_lpcValues_参数的值可以为零。</span><span class="sxs-lookup"><span data-stu-id="a7757-136">The value of the  _lpcValues_ parameter can be zero if  _lppProps_ is NULL.</span></span> 
    
 <span data-ttu-id="a7757-137">_lppProps_</span><span class="sxs-lookup"><span data-stu-id="a7757-137">_lppProps_</span></span>
  
> <span data-ttu-id="a7757-138">[in, out]指向**SPropValue**结构数组的指针, 该数组包含**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) 属性和相应的文件夹项标识符属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="a7757-138">[in, out] Pointer to a pointer to an array of **SPropValue** structures that contains property values for the **PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md)) property and for the appropriate folder entry identifier properties.</span></span> <span data-ttu-id="a7757-139">如果**HrValidateIPMSubtree**在邮件存储区中创建收件箱, 则**SPropValue**数组包含一个带有编码为`PROP_TAG(PT_BINARY, PROP_ID_NULL)`的特殊属性标记的收件箱条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a7757-139">If **HrValidateIPMSubtree** creates an Inbox in the message store, the **SPropValue** array includes an Inbox entry identifier with a special property tag coded as  `PROP_TAG(PT_BINARY, PROP_ID_NULL)`.</span></span> <span data-ttu-id="a7757-140">_lppProps_参数可以为 NULL, 指示调用实现不要求返回**SPropValue**数组。</span><span class="sxs-lookup"><span data-stu-id="a7757-140">The  _lppProps_ parameter can be NULL, indicating that the calling implementation does not require that an **SPropValue** array be returned.</span></span> 
    
 <span data-ttu-id="a7757-141">_lppMapiError_</span><span class="sxs-lookup"><span data-stu-id="a7757-141">_lppMapiError_</span></span>
  
> <span data-ttu-id="a7757-142">排除指向包含错误的版本、组件和上下文信息的[MAPIERROR](mapierror.md)结构的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a7757-142">[out] Pointer to a pointer to a [MAPIERROR](mapierror.md) structure that contains version, component, and context information for an error.</span></span> <span data-ttu-id="a7757-143">如果不返回**MAPIERROR**结构, 则将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a7757-143">The  _lppMAPIError_ parameter is set to NULL if no **MAPIERROR** structure is returned.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a7757-144">返回值</span><span class="sxs-lookup"><span data-stu-id="a7757-144">Return value</span></span>

<span data-ttu-id="a7757-145">无。</span><span class="sxs-lookup"><span data-stu-id="a7757-145">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a7757-146">说明</span><span class="sxs-lookup"><span data-stu-id="a7757-146">Remarks</span></span>

<span data-ttu-id="a7757-147">MAPI 在内部使用**HrValidateIPMSubtree**函数在首次打开存储库时或在将存储创建为默认存储时在邮件存储中构建标准的 IPM 子树。</span><span class="sxs-lookup"><span data-stu-id="a7757-147">MAPI uses the **HrValidateIPMSubtree** function internally to construct the standard IPM subtree in a message store when the store is first opened, or when a store is made the default store.</span></span> <span data-ttu-id="a7757-148">客户端应用程序还可以使用此函数验证或修复标准邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7757-148">This function can also be used by client applications to validate or repair standard message folders.</span></span> 
  
 <span data-ttu-id="a7757-149">**HrValidateIPMSubtree**始终在存储区的根文件夹和 ipm 子树文件夹中的 "已删除邮件" 文件夹中创建搜索根和 IPM 子树文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7757-149">**HrValidateIPMSubtree** always creates the Search Root and IPM Subtree folders in the store's root folder and the Deleted Items folder in the IPM Subtree folder.</span></span> <span data-ttu-id="a7757-150">ipm 子树文件夹是该邮件存储区中 ipm 层次结构的根。</span><span class="sxs-lookup"><span data-stu-id="a7757-150">The IPM Subtree folder is the root of the IPM hierarchy in that message store.</span></span> <span data-ttu-id="a7757-151">搜索根文件夹可用作搜索结果文件夹的子树的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7757-151">The Search Root folder can be used as the root of a subtree for search-results folders.</span></span> 
  
<span data-ttu-id="a7757-152">IPM 客户端应显示其文件夹视图 (从 IPM 子树根文件夹开始, 并在其下显示子文件夹)。</span><span class="sxs-lookup"><span data-stu-id="a7757-152">IPM clients should display their folder view starting at the IPM subtree root folder and showing child folders beneath it.</span></span> <span data-ttu-id="a7757-153">邮件存储区的根文件夹中的信息不应出现在客户端的用户界面中。</span><span class="sxs-lookup"><span data-stu-id="a7757-153">Information in the root folder of a message store should not appear in a client's user interface.</span></span> <span data-ttu-id="a7757-154">此功能意味着, 如果客户端必须隐藏信息, 则可以将信息放在 IPM 子树根目录中, 该目录对用户是不可见的。</span><span class="sxs-lookup"><span data-stu-id="a7757-154">This functionality means that if a client must hide information, the information can be put in the IPM subtree root directory, where it is not visible to the user.</span></span> <span data-ttu-id="a7757-155">相比之下, 要求邮件和文件夹对用户不可见的非 IPM 应用程序 (例如, 在基于服务器的邮件存储区中) 可以将它们放在 IPM 层次结构之外。</span><span class="sxs-lookup"><span data-stu-id="a7757-155">In contrast, non-IPM applications that require messages and folders to be invisible to the user, for example in a server-based message store, can put them outside the IPM hierarchy.</span></span> 
  
 <span data-ttu-id="a7757-156">**HrValidateIPMSubtree**设置**PR_VALID_FOLDER_MASK**属性, 以指示它所创建的每个 IPM 文件夹是否都有一个有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a7757-156">**HrValidateIPMSubtree** sets the **PR_VALID_FOLDER_MASK** property to indicate whether each IPM folder it creates has a valid entry identifier.</span></span> <span data-ttu-id="a7757-157">邮件存储区的以下条目标识符属性将设置为相应文件夹的条目标识符, 并在_lppProps_参数中返回, 以及**PR_VALID_FOLDER_MASK**:</span><span class="sxs-lookup"><span data-stu-id="a7757-157">The following entry identifier properties of the message store are set to the entry identifiers of the corresponding folders and returned in the  _lppProps_ parameter along with **PR_VALID_FOLDER_MASK**:</span></span> 
  
 <span data-ttu-id="a7757-158">**PR_COMMON_VIEWS_ENTRYID**([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-158">**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-159">**PR_FINDER_ENTRYID**([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-159">**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-160">**PR_IPM_OUTBOX_ENTRYID**([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-160">**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-161">**PR_IPM_SENTMAIL_ENTRYID**([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-161">**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-162">**PR_IPM_SUBTREE_ENTRYID**([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-162">**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-163">**PR_IPM_WASTEBASKET_ENTRYID**([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-163">**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-164">**PR_VIEWS_ENTRYID**([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a7757-164">**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))</span></span>
  
> <span data-ttu-id="a7757-165">用于 IPM 收件箱的占位符[PROP_TAG](prop_tag.md) (PT_BINARY, PROP_ID_NULL)。</span><span class="sxs-lookup"><span data-stu-id="a7757-165">A placeholder [PROP_TAG](prop_tag.md) for the IPM Inbox (PT_BINARY, PROP_ID_NULL).</span></span> 
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="a7757-166">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a7757-166">MFCMAPI reference</span></span>

<span data-ttu-id="a7757-167">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a7757-167">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a7757-168">**文件**</span><span class="sxs-lookup"><span data-stu-id="a7757-168">**File**</span></span>|<span data-ttu-id="a7757-169">**函数**</span><span class="sxs-lookup"><span data-stu-id="a7757-169">**Function**</span></span>|<span data-ttu-id="a7757-170">**备注**</span><span class="sxs-lookup"><span data-stu-id="a7757-170">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7757-171">MstStoreDlg</span><span class="sxs-lookup"><span data-stu-id="a7757-171">MstStoreDlg.cpp</span></span>  <br/> |<span data-ttu-id="a7757-172">CMsgStoreDlg:: OnValidateIPMSubtree</span><span class="sxs-lookup"><span data-stu-id="a7757-172">CMsgStoreDlg::OnValidateIPMSubtree</span></span>  <br/> |<span data-ttu-id="a7757-173">MFCMAPI 使用**HrValidateIPMSubtree**方法将标准文件夹添加到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="a7757-173">MFCMAPI uses the **HrValidateIPMSubtree** method to add standard folders to a message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a7757-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7757-174">See also</span></span>



[<span data-ttu-id="a7757-175">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="a7757-175">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)


[<span data-ttu-id="a7757-176">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a7757-176">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

