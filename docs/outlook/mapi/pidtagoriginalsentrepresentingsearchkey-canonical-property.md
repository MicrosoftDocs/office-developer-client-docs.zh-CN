---
title: PidTagOriginalSentRepresentingSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingSearchKey
api_type:
- COM
ms.assetid: 0fb1b803-f8b4-4d6d-8e2a-836daa98ac63
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5c3c8f121423cdd15d7f8e8beee80b667b29a09b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585519"
---
# <a name="pidtagoriginalsentrepresentingsearchkey-canonical-property"></a><span data-ttu-id="cd34f-103">PidTagOriginalSentRepresentingSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd34f-103">PidTagOriginalSentRepresentingSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="cd34f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd34f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd34f-105">包含搜索关键字的名义原始邮件已发送的消息用户。</span><span class="sxs-lookup"><span data-stu-id="cd34f-105">Contains the search key of the messaging user on whose behalf the original message was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cd34f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cd34f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cd34f-107">PR_ORIGINAL_SENT_REPRESENTING_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="cd34f-107">PR_ORIGINAL_SENT_REPRESENTING_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="cd34f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="cd34f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cd34f-109">0x005F</span><span class="sxs-lookup"><span data-stu-id="cd34f-109">0x005F</span></span>  <br/> |
|<span data-ttu-id="cd34f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cd34f-110">Data type:</span></span>  <br/> |<span data-ttu-id="cd34f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cd34f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="cd34f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cd34f-112">Area:</span></span>  <br/> |<span data-ttu-id="cd34f-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="cd34f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cd34f-114">注解</span><span class="sxs-lookup"><span data-stu-id="cd34f-114">Remarks</span></span>

<span data-ttu-id="cd34f-115">此属性是原始表示邮件发件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="cd34f-115">This property is one of the address properties for the original represented sender of a message.</span></span> <span data-ttu-id="cd34f-116">在对话的线程中使用它。</span><span class="sxs-lookup"><span data-stu-id="cd34f-116">It is used in a conversation thread.</span></span>
  
<span data-ttu-id="cd34f-117">发送一条消息，代表另一个客户端的客户端应用程序应将此属性设置为在首次提交邮件**PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="cd34f-117">A client application sending a message on behalf of another client should set this property to the value of the **PR_SENT_REPRESENTING_SEARCH_KEY** ([PidTagSentRepresentingSearchKey](pidtagsentrepresentingsearchkey-canonical-property.md)) property at the first submission of the message.</span></span> <span data-ttu-id="cd34f-118">设置后，它应永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="cd34f-118">Once set, it should never be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cd34f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="cd34f-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cd34f-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="cd34f-120">Protocol specifications</span></span>

<span data-ttu-id="cd34f-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd34f-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cd34f-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="cd34f-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cd34f-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd34f-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cd34f-124">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="cd34f-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cd34f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="cd34f-125">Header files</span></span>

<span data-ttu-id="cd34f-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cd34f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="cd34f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cd34f-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="cd34f-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cd34f-128">Mapitags.h</span></span>
  
> <span data-ttu-id="cd34f-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cd34f-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cd34f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd34f-130">See also</span></span>



[<span data-ttu-id="cd34f-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cd34f-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cd34f-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd34f-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cd34f-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cd34f-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cd34f-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cd34f-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

