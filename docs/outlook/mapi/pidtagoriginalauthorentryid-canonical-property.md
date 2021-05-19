---
title: PidTagOriginalAuthorEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorEntryId
api_type:
- COM
ms.assetid: 34654660-b003-42f5-9fcd-24ebaccd735d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 866c28bc08f669d18487c99c9a13bc7347b605fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425587"
---
# <a name="pidtagoriginalauthorentryid-canonical-property"></a><span data-ttu-id="d1921-103">PidTagOriginalAuthorEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1921-103">PidTagOriginalAuthorEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="d1921-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1921-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1921-105">包含邮件第一个版本（即转发或答复前的邮件）的作者的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d1921-105">Contains the entry identifier of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1921-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d1921-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d1921-107">PR_ORIGINAL_AUTHOR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d1921-107">PR_ORIGINAL_AUTHOR_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="d1921-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d1921-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d1921-109">0x004C</span><span class="sxs-lookup"><span data-stu-id="d1921-109">0x004C</span></span>  <br/> |
|<span data-ttu-id="d1921-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d1921-110">Data type:</span></span>  <br/> |<span data-ttu-id="d1921-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d1921-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d1921-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d1921-112">Area:</span></span>  <br/> |<span data-ttu-id="d1921-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="d1921-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1921-114">备注</span><span class="sxs-lookup"><span data-stu-id="d1921-114">Remarks</span></span>

<span data-ttu-id="d1921-115">此属性是邮件作者的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="d1921-115">This property is one of the address properties for the author of a message.</span></span> <span data-ttu-id="d1921-116">首次提交邮件时，客户端应用程序应该将此属性设置为 PR_SENDER_ENTRYID ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="d1921-116">At first submission of the message, the client application should set this property to the value of **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)).</span></span> <span data-ttu-id="d1921-117">转发或答复邮件时从不更改。</span><span class="sxs-lookup"><span data-stu-id="d1921-117">It is never changed when the message is forwarded or replied to.</span></span> 
  
<span data-ttu-id="d1921-118">原始作者属性允许保留来自本地邮件域外部的信息。</span><span class="sxs-lookup"><span data-stu-id="d1921-118">The original author property allows for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="d1921-119">当邮件从另一个消息域（如 Internet）到达时，此属性提供了一种确保原始信息不会丢失的方法。</span><span class="sxs-lookup"><span data-stu-id="d1921-119">When a message arrives from another messaging domain, such as from the Internet, this property provides a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d1921-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="d1921-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d1921-121">头文件</span><span class="sxs-lookup"><span data-stu-id="d1921-121">Header files</span></span>

<span data-ttu-id="d1921-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d1921-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="d1921-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d1921-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="d1921-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d1921-124">Mapitags.h</span></span>
  
> <span data-ttu-id="d1921-125">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d1921-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1921-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1921-126">See also</span></span>



[<span data-ttu-id="d1921-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d1921-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d1921-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1921-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d1921-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d1921-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d1921-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1921-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

