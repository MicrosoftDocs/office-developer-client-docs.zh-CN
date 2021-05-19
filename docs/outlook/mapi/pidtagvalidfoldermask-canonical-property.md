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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427792"
---
# <a name="pidtagvalidfoldermask-canonical-property"></a><span data-ttu-id="44490-103">PidTagValidFolderMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="44490-103">PidTagValidFolderMask Canonical Property</span></span>

  
  
<span data-ttu-id="44490-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="44490-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="44490-105">包含指示邮件存储中文件夹的条目标识符的有效性的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="44490-105">Contains a bitmask of flags that indicate the validity of the entry identifiers of the folders in a message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="44490-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="44490-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="44490-107">PR_VALID_FOLDER_MASK</span><span class="sxs-lookup"><span data-stu-id="44490-107">PR_VALID_FOLDER_MASK</span></span>  <br/> |
|<span data-ttu-id="44490-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="44490-108">Identifier:</span></span>  <br/> |<span data-ttu-id="44490-109">0x35DF</span><span class="sxs-lookup"><span data-stu-id="44490-109">0x35DF</span></span>  <br/> |
|<span data-ttu-id="44490-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="44490-110">Data type:</span></span>  <br/> |<span data-ttu-id="44490-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="44490-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="44490-112">区域：</span><span class="sxs-lookup"><span data-stu-id="44490-112">Area:</span></span>  <br/> |<span data-ttu-id="44490-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="44490-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="44490-114">备注</span><span class="sxs-lookup"><span data-stu-id="44490-114">Remarks</span></span>

<span data-ttu-id="44490-115">如果用户删除该文件夹或邮件存储已损坏，文件夹的条目标识符可能变为无效。</span><span class="sxs-lookup"><span data-stu-id="44490-115">A folder's entry identifier can become invalid if a user deletes the folder or if the message store becomes corrupted.</span></span>
  
<span data-ttu-id="44490-116">可以为位掩码设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="44490-116">One or more of the following flags can be set for the bitmask:</span></span> 
  
<span data-ttu-id="44490-117">FOLDER_COMMON_VIEWS_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-117">FOLDER_COMMON_VIEWS_VALID</span></span> 
  
> <span data-ttu-id="44490-118">通用视图文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-118">The common views folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-119">请参阅 **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-119">See **PR_COMMON_VIEWS_ENTRYID** ([PidTagCommonViewsEntryId](pidtagcommonviewsentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="44490-120">FOLDER_FINDER_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-120">FOLDER_FINDER_VALID</span></span> 
  
> <span data-ttu-id="44490-121">查找器文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-121">The finder folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-122">请参阅 **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-122">See **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md)).</span></span> 
    
<span data-ttu-id="44490-123">FOLDER_IPM_INBOX_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-123">FOLDER_IPM_INBOX_VALID</span></span> 
  
> <span data-ttu-id="44490-124">IPM (接收) 邮件具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-124">The interpersonal message (IPM) receive folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-125">请参阅 [IMsgStore：：GetReceiveFolder](imsgstore-getreceivefolder.md)。</span><span class="sxs-lookup"><span data-stu-id="44490-125">See [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md).</span></span> 
    
<span data-ttu-id="44490-126">FOLDER_IPM_OUTBOX_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-126">FOLDER_IPM_OUTBOX_VALID</span></span> 
  
> <span data-ttu-id="44490-127">IPM 发件箱文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-127">The IPM Outbox folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-128">请参阅 **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-128">See **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)).</span></span> 
    
<span data-ttu-id="44490-129">FOLDER_IPM_SENTMAIL_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-129">FOLDER_IPM_SENTMAIL_VALID</span></span> 
  
> <span data-ttu-id="44490-130">"IPM 已发送的项目"文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-130">The IPM Sent Items folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-131">请参阅 **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-131">See **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="44490-132">FOLDER_IPM_SUBTREE_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-132">FOLDER_IPM_SUBTREE_VALID</span></span> 
  
> <span data-ttu-id="44490-133">IPM 文件夹子树具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-133">The IPM folder subtree has a valid entry identifier.</span></span> <span data-ttu-id="44490-134">请参阅 **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-134">See **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="44490-135">FOLDER_IPM_WASTEBASKET_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-135">FOLDER_IPM_WASTEBASKET_VALID</span></span> 
  
> <span data-ttu-id="44490-136">"IPM 已删除邮件"文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-136">The IPM Deleted Items folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-137">请参阅 **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-137">See **PR_IPM_WASTEBASKET_ENTRYID** ([PidTagIpmWastebasketEntryId](pidtagipmwastebasketentryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="44490-138">FOLDER_VIEWS_VALID</span><span class="sxs-lookup"><span data-stu-id="44490-138">FOLDER_VIEWS_VALID</span></span> 
  
> <span data-ttu-id="44490-139">views 文件夹具有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="44490-139">The views folder has a valid entry identifier.</span></span> <span data-ttu-id="44490-140">请参阅 **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="44490-140">See **PR_VIEWS_ENTRYID** ([PidTagViewsEntryId](pidtagviewsentryid-canonical-property.md)).</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="44490-141">相关资源</span><span class="sxs-lookup"><span data-stu-id="44490-141">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="44490-142">头文件</span><span class="sxs-lookup"><span data-stu-id="44490-142">Header files</span></span>

<span data-ttu-id="44490-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="44490-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="44490-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="44490-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="44490-145">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="44490-145">Mapitags.h</span></span>
  
> <span data-ttu-id="44490-146">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="44490-146">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="44490-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44490-147">See also</span></span>



[<span data-ttu-id="44490-148">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="44490-148">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="44490-149">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="44490-149">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="44490-150">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="44490-150">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="44490-151">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="44490-151">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

