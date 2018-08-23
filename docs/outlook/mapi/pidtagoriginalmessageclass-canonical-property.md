---
title: PidTagOriginalMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalMessageClass
api_type:
- COM
ms.assetid: 49deb153-03c6-4be2-a3a5-53cca01accba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0abd3618f7a1586d8ca786fc1b6802c17e0f0f1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573115"
---
# <a name="pidtagoriginalmessageclass-canonical-property"></a><span data-ttu-id="ac095-103">PidTagOriginalMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac095-103">PidTagOriginalMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="ac095-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ac095-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ac095-105">包含用于在报表中使用的原始消息的类。</span><span class="sxs-lookup"><span data-stu-id="ac095-105">Contains the class of the original message for use in a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac095-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ac095-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ac095-107">PR_ORIG_MESSAGE_CLASS，PR_ORIG_MESSAGE_CLASS_A，PR_ORIG_MESSAGE_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="ac095-107">PR_ORIG_MESSAGE_CLASS, PR_ORIG_MESSAGE_CLASS_A, PR_ORIG_MESSAGE_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="ac095-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ac095-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ac095-109">0x004B</span><span class="sxs-lookup"><span data-stu-id="ac095-109">0x004B</span></span>  <br/> |
|<span data-ttu-id="ac095-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ac095-110">Data type:</span></span>  <br/> |<span data-ttu-id="ac095-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ac095-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ac095-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ac095-112">Area:</span></span>  <br/> |<span data-ttu-id="ac095-113">安全邮件属性</span><span class="sxs-lookup"><span data-stu-id="ac095-113">Secure Messaging Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac095-114">注解</span><span class="sxs-lookup"><span data-stu-id="ac095-114">Remarks</span></span>

<span data-ttu-id="ac095-115">这些属性包含**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性为其生成报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="ac095-115">These properties contain a copy of the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the message for which the report is being generated.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ac095-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="ac095-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ac095-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="ac095-117">Protocol specifications</span></span>

<span data-ttu-id="ac095-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac095-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac095-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ac095-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ac095-120">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac095-120">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac095-121">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="ac095-121">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ac095-122">头文件</span><span class="sxs-lookup"><span data-stu-id="ac095-122">Header files</span></span>

<span data-ttu-id="ac095-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ac095-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="ac095-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ac095-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="ac095-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ac095-125">Mapitags.h</span></span>
  
> <span data-ttu-id="ac095-126">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ac095-126">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac095-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac095-127">See also</span></span>



[<span data-ttu-id="ac095-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ac095-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ac095-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac095-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ac095-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ac095-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ac095-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac095-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

