---
title: PidTagConversationKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 52c97d6c-7f4b-4522-aeac-0c1ed8475952
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 00c65dae9bc29fe9cdb310b819ba99d6d46ebfe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334697"
---
# <a name="pidtagconversationkey-canonical-property"></a><span data-ttu-id="33f8e-103">PidTagConversationKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="33f8e-103">PidTagConversationKey Canonical Property</span></span>

  
  
<span data-ttu-id="33f8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33f8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33f8e-105">包含仅在找到 IPM 时在 Microsoft Outlook中使用的对话 **密钥。MessageManager** 邮件，例如包含 POST Office Protocol (POP3) 历史记录的邮件。</span><span class="sxs-lookup"><span data-stu-id="33f8e-105">Contains the conversation key used in Microsoft Outlook only when locating **IPM.MessageManager** messages, such as the message that contains download history for a Post Office Protocol (POP3) account.</span></span> <span data-ttu-id="33f8e-106">此属性在 Microsoft Exchange Server 中已Microsoft Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="33f8e-106">This property has been deprecated in Microsoft Exchange Server.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="33f8e-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="33f8e-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="33f8e-108">PR_CONVERSATION_KEY</span><span class="sxs-lookup"><span data-stu-id="33f8e-108">PR_CONVERSATION_KEY</span></span>  <br/> |
|<span data-ttu-id="33f8e-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="33f8e-109">Identifier:</span></span>  <br/> |<span data-ttu-id="33f8e-110">0x000B</span><span class="sxs-lookup"><span data-stu-id="33f8e-110">0x000B</span></span>  <br/> |
|<span data-ttu-id="33f8e-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="33f8e-111">Data type:</span></span>  <br/> |<span data-ttu-id="33f8e-112">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="33f8e-112">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="33f8e-113">区域：</span><span class="sxs-lookup"><span data-stu-id="33f8e-113">Area:</span></span>  <br/> |<span data-ttu-id="33f8e-114">常规消息</span><span class="sxs-lookup"><span data-stu-id="33f8e-114">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33f8e-115">备注</span><span class="sxs-lookup"><span data-stu-id="33f8e-115">Remarks</span></span>

<span data-ttu-id="33f8e-116">当作为对话访问电子邮件并将邮件属性转换为传输中性封装格式 [ (TNEF ](transport-neutral-encapsulation-format-tnef.md)) 时，请勿使用此属性;请改为使用 [PidTagConversationIndex](pidtagconversationindex-canonical-property.md) 和 [PidTagConversationTopic](pidtagconversationtopic-canonical-property.md) 规范属性。</span><span class="sxs-lookup"><span data-stu-id="33f8e-116">When accessing email messages as conversations and converting message properties to [Transport-Neutral Encapsulation Format (TNEF)](transport-neutral-encapsulation-format-tnef.md), do not use this property; instead, use the [PidTagConversationIndex](pidtagconversationindex-canonical-property.md) and [PidTagConversationTopic](pidtagconversationtopic-canonical-property.md) canonical properties.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="33f8e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="33f8e-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="33f8e-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="33f8e-118">Protocol specifications</span></span>

<span data-ttu-id="33f8e-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33f8e-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33f8e-120">提供对相关协议Microsoft Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="33f8e-120">Provides references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="33f8e-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33f8e-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33f8e-122">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="33f8e-122">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
<span data-ttu-id="33f8e-123">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33f8e-123">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33f8e-124">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="33f8e-124">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="33f8e-125">头文件</span><span class="sxs-lookup"><span data-stu-id="33f8e-125">Header files</span></span>

<span data-ttu-id="33f8e-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="33f8e-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="33f8e-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="33f8e-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="33f8e-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="33f8e-128">Mapitags.h</span></span>
  
> <span data-ttu-id="33f8e-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="33f8e-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="33f8e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33f8e-130">See also</span></span>



[<span data-ttu-id="33f8e-131">IPM 子树</span><span class="sxs-lookup"><span data-stu-id="33f8e-131">IPM Subtree</span></span>](ipm-subtree.md)
  
[<span data-ttu-id="33f8e-132">MAPI 特殊文件夹</span><span class="sxs-lookup"><span data-stu-id="33f8e-132">MAPI Special Folders</span></span>](mapi-special-folders.md)
  
[<span data-ttu-id="33f8e-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="33f8e-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="33f8e-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="33f8e-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="33f8e-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="33f8e-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="33f8e-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="33f8e-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

