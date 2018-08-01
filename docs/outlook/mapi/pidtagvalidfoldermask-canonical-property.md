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
ms.openlocfilehash: ae09723c78fe4e333fb5c46e8c79da4b77c0b331
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778535"
---
# <a name="pidtagvalidfoldermask-canonical-property"></a><span data-ttu-id="ba605-103">PidTagValidFolderMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba605-103">PidTagValidFolderMask Canonical Property</span></span>

  
  
<span data-ttu-id="ba605-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ba605-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ba605-105">包含这些标志指示邮件存储区中的文件夹的项标识符的有效性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ba605-105">Contains a bitmask of flags that indicate the validity of the entry identifiers of the folders in a message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ba605-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ba605-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ba605-107">PR_VALID_FOLDER_MASK</span><span class="sxs-lookup"><span data-stu-id="ba605-107">PR_VALID_FOLDER_MASK</span></span>  <br/> |
|<span data-ttu-id="ba605-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ba605-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ba605-109">0x35DF</span><span class="sxs-lookup"><span data-stu-id="ba605-109">0x35DF</span></span>  <br/> |
|<span data-ttu-id="ba605-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ba605-110">Data type:</span></span>  <br/> |<span data-ttu-id="ba605-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ba605-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ba605-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ba605-112">Area:</span></span>  <br/> |<span data-ttu-id="ba605-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="ba605-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ba605-114">说明</span><span class="sxs-lookup"><span data-stu-id="ba605-114">Remarks</span></span>

<span data-ttu-id="ba605-115">如果用户删除文件夹，或者如果消息存储已损坏，某个文件夹的条目标识符可以成为无效。</span><span class="sxs-lookup"><span data-stu-id="ba605-115">A folder's entry identifier can become invalid if a user deletes the folder or if the message store becomes corrupted.</span></span>
  
<span data-ttu-id="ba605-116">可以为位掩码设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="ba605-116">One or more of the following flags can be set for the bitmask:</span></span> 
  
<span data-ttu-id="ba605-117">FOLDER_COMMON_VIEWS_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-117">FOLDER_COMMON_VIEWS_VALID</span></span> 
  
> <span data-ttu-id="ba605-118">公共视图文件夹具有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-118">The common views folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-119">请参阅**PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-119">See **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="ba605-120">FOLDER_FINDER_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-120">FOLDER_FINDER_VALID</span></span> 
  
> <span data-ttu-id="ba605-121">Finder 文件夹有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-121">The finder folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-122">请参阅**PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-122">See **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)).</span></span> 
    
<span data-ttu-id="ba605-123">FOLDER_IPM_INBOX_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-123">FOLDER_IPM_INBOX_VALID</span></span> 
  
> <span data-ttu-id="ba605-124">人际邮件 (IPM) 接收文件夹都有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-124">The interpersonal message (IPM) receive folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-125">请参阅[IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md)。</span><span class="sxs-lookup"><span data-stu-id="ba605-125">See [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md).</span></span> 
    
<span data-ttu-id="ba605-126">FOLDER_IPM_OUTBOX_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-126">FOLDER_IPM_OUTBOX_VALID</span></span> 
  
> <span data-ttu-id="ba605-127">IPM 发件箱文件夹具有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-127">The IPM Outbox folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-128">请参阅**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-128">See **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)).</span></span> 
    
<span data-ttu-id="ba605-129">FOLDER_IPM_SENTMAIL_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-129">FOLDER_IPM_SENTMAIL_VALID</span></span> 
  
> <span data-ttu-id="ba605-130">IPM 发送邮件文件夹具有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-130">The IPM Sent Items folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-131">请参阅**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-131">See **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="ba605-132">FOLDER_IPM_SUBTREE_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-132">FOLDER_IPM_SUBTREE_VALID</span></span> 
  
> <span data-ttu-id="ba605-133">IPM 文件夹子树有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-133">The IPM folder subtree has a valid entry identifier.</span></span> <span data-ttu-id="ba605-134">请参阅**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-134">See **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="ba605-135">FOLDER_IPM_WASTEBASKET_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-135">FOLDER_IPM_WASTEBASKET_VALID</span></span> 
  
> <span data-ttu-id="ba605-136">IPM 已删除邮件文件夹具有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-136">The IPM Deleted Items folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-137">请参阅**PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-137">See **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="ba605-138">FOLDER_VIEWS_VALID</span><span class="sxs-lookup"><span data-stu-id="ba605-138">FOLDER_VIEWS_VALID</span></span> 
  
> <span data-ttu-id="ba605-139">在 views 文件夹有一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="ba605-139">The views folder has a valid entry identifier.</span></span> <span data-ttu-id="ba605-140">请参阅**PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ba605-140">See **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)).</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="ba605-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="ba605-141">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ba605-142">头文件</span><span class="sxs-lookup"><span data-stu-id="ba605-142">Header files</span></span>

<span data-ttu-id="ba605-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ba605-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="ba605-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ba605-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="ba605-145">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ba605-145">Mapitags.h</span></span>
  
> <span data-ttu-id="ba605-146">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ba605-146">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ba605-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba605-147">See also</span></span>



[<span data-ttu-id="ba605-148">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ba605-148">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ba605-149">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba605-149">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ba605-150">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ba605-150">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ba605-151">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ba605-151">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

