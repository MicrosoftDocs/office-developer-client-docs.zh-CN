---
title: PidTagOriginalSentRepresentingEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingEntryId
api_type:
- COM
ms.assetid: ece3df57-47f3-4d27-854f-b511c920ac75
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eaf91472794c5188a63897bccaa900c4882407bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341753"
---
# <a name="pidtagoriginalsentrepresentingentryid-canonical-property"></a><span data-ttu-id="7b695-103">PidTagOriginalSentRepresentingEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b695-103">PidTagOriginalSentRepresentingEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="7b695-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b695-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b695-105">包含邮件用户的条目标识符, 该用户代表其发送原始邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="7b695-105">Contains the entry identifier of the messaging user on whose behalf the original message was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7b695-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7b695-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7b695-107">PR_ORIGINAL_SENT_REPRESENTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="7b695-107">PR_ORIGINAL_SENT_REPRESENTING_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="7b695-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7b695-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7b695-109">0x005E</span><span class="sxs-lookup"><span data-stu-id="7b695-109">0x005E</span></span>  <br/> |
|<span data-ttu-id="7b695-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7b695-110">Data type:</span></span>  <br/> |<span data-ttu-id="7b695-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="7b695-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="7b695-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7b695-112">Area:</span></span>  <br/> |<span data-ttu-id="7b695-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="7b695-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7b695-114">注解</span><span class="sxs-lookup"><span data-stu-id="7b695-114">Remarks</span></span>

<span data-ttu-id="7b695-115">此属性是邮件的原始发件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="7b695-115">This property is one of the address properties for the original represented sender of a message.</span></span> <span data-ttu-id="7b695-116">它在会话线程中使用。</span><span class="sxs-lookup"><span data-stu-id="7b695-116">It is used in a conversation thread.</span></span>
  
<span data-ttu-id="7b695-117">代表另一个客户端发送邮件的客户端应用程序应在第一次提交邮件时将此属性设置为**PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="7b695-117">A client application sending a message on behalf of another client should set this property to the value of the **PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) property at the first submission of the message.</span></span> <span data-ttu-id="7b695-118">设置后, 决不能更改它。</span><span class="sxs-lookup"><span data-stu-id="7b695-118">Once set, it should never be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7b695-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="7b695-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7b695-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="7b695-120">Protocol specifications</span></span>

<span data-ttu-id="7b695-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7b695-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7b695-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7b695-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7b695-123">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7b695-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7b695-124">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7b695-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7b695-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7b695-125">Header files</span></span>

<span data-ttu-id="7b695-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7b695-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7b695-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7b695-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="7b695-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="7b695-128">Mapitags.h</span></span>
  
> <span data-ttu-id="7b695-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7b695-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b695-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b695-130">See also</span></span>



[<span data-ttu-id="7b695-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7b695-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7b695-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b695-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7b695-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7b695-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7b695-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7b695-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

