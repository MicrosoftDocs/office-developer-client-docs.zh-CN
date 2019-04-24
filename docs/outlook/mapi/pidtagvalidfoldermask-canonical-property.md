---
title: PidTagValidFolderMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagValidFolderMask
api_type:
- COM
ms.assetid: 83a44aee-5269-42a8-8078-4bc063bb6e29
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 925e0eb60d55349ded114b827b6ca67e3b5ac1ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360744"
---
# <a name="pidtagvalidfoldermask-canonical-property"></a><span data-ttu-id="379bb-103">PidTagValidFolderMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="379bb-103">PidTagValidFolderMask Canonical Property</span></span>

  
  
<span data-ttu-id="379bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="379bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="379bb-105">包含标志的位掩码, 用于指示邮件存储区中的文件夹的条目标识符的有效性。</span><span class="sxs-lookup"><span data-stu-id="379bb-105">Contains a bitmask of flags that indicate the validity of the entry identifiers of the folders in a message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="379bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="379bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="379bb-107">PR_VALID_FOLDER_MASK</span><span class="sxs-lookup"><span data-stu-id="379bb-107">PR_VALID_FOLDER_MASK</span></span>  <br/> |
|<span data-ttu-id="379bb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="379bb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="379bb-109">0x35DF</span><span class="sxs-lookup"><span data-stu-id="379bb-109">0x35DF</span></span>  <br/> |
|<span data-ttu-id="379bb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="379bb-110">Data type:</span></span>  <br/> |<span data-ttu-id="379bb-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="379bb-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="379bb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="379bb-112">Area:</span></span>  <br/> |<span data-ttu-id="379bb-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="379bb-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="379bb-114">注解</span><span class="sxs-lookup"><span data-stu-id="379bb-114">Remarks</span></span>

<span data-ttu-id="379bb-115">如果用户删除文件夹或邮件存储区损坏, 则文件夹的条目标识符可能会变得无效。</span><span class="sxs-lookup"><span data-stu-id="379bb-115">A folder's entry identifier can become invalid if a user deletes the folder or if the message store becomes corrupted.</span></span>
  
<span data-ttu-id="379bb-116">可以为位掩码设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="379bb-116">One or more of the following flags can be set for the bitmask:</span></span> 
  
<span data-ttu-id="379bb-117">FOLDER_COMMON_VIEWS_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-117">FOLDER_COMMON_VIEWS_VALID</span></span> 
  
> <span data-ttu-id="379bb-118">"常见视图" 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-118">The common views folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-119">请参阅**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-119">See **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="379bb-120">FOLDER_FINDER_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-120">FOLDER_FINDER_VALID</span></span> 
  
> <span data-ttu-id="379bb-121">finder 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-121">The finder folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-122">请参阅**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-122">See **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)).</span></span> 
    
<span data-ttu-id="379bb-123">FOLDER_IPM_INBOX_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-123">FOLDER_IPM_INBOX_VALID</span></span> 
  
> <span data-ttu-id="379bb-124">人际邮件 (IPM) 接收文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-124">The interpersonal message (IPM) receive folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-125">请参阅[IMsgStore:: GetReceiveFolder](imsgstore-getreceivefolder.md)。</span><span class="sxs-lookup"><span data-stu-id="379bb-125">See [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md).</span></span> 
    
<span data-ttu-id="379bb-126">FOLDER_IPM_OUTBOX_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-126">FOLDER_IPM_OUTBOX_VALID</span></span> 
  
> <span data-ttu-id="379bb-127">IPM "发件箱" 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-127">The IPM Outbox folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-128">请参阅**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-128">See **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)).</span></span> 
    
<span data-ttu-id="379bb-129">FOLDER_IPM_SENTMAIL_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-129">FOLDER_IPM_SENTMAIL_VALID</span></span> 
  
> <span data-ttu-id="379bb-130">"IPM 已发送邮件" 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-130">The IPM Sent Items folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-131">请参阅**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-131">See **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="379bb-132">FOLDER_IPM_SUBTREE_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-132">FOLDER_IPM_SUBTREE_VALID</span></span> 
  
> <span data-ttu-id="379bb-133">IPM 文件夹子树具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-133">The IPM folder subtree has a valid entry identifier.</span></span> <span data-ttu-id="379bb-134">请参阅**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-134">See **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="379bb-135">FOLDER_IPM_WASTEBASKET_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-135">FOLDER_IPM_WASTEBASKET_VALID</span></span> 
  
> <span data-ttu-id="379bb-136">"IPM 已删除邮件" 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-136">The IPM Deleted Items folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-137">请参阅**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-137">See **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="379bb-138">FOLDER_VIEWS_VALID</span><span class="sxs-lookup"><span data-stu-id="379bb-138">FOLDER_VIEWS_VALID</span></span> 
  
> <span data-ttu-id="379bb-139">views 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="379bb-139">The views folder has a valid entry identifier.</span></span> <span data-ttu-id="379bb-140">请参阅**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="379bb-140">See **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)).</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="379bb-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="379bb-141">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="379bb-142">头文件</span><span class="sxs-lookup"><span data-stu-id="379bb-142">Header files</span></span>

<span data-ttu-id="379bb-143">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="379bb-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="379bb-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="379bb-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="379bb-145">Mapitags</span><span class="sxs-lookup"><span data-stu-id="379bb-145">Mapitags.h</span></span>
  
> <span data-ttu-id="379bb-146">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="379bb-146">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="379bb-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="379bb-147">See also</span></span>



[<span data-ttu-id="379bb-148">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="379bb-148">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="379bb-149">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="379bb-149">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="379bb-150">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="379bb-150">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="379bb-151">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="379bb-151">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

