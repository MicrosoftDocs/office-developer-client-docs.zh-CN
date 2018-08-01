---
title: PidTagUrlComponentName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUrlComponentName
api_type:
- COM
ms.assetid: a21906f9-5408-41ba-a89b-273ab60eeef3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3a2b0939bbfa5143e4bd99e74b0f84e3ca7efb12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778528"
---
# <a name="pidtagurlcomponentname-canonical-property"></a><span data-ttu-id="a5f2d-103">PidTagUrlComponentName 规范属性</span><span class="sxs-lookup"><span data-stu-id="a5f2d-103">PidTagUrlComponentName Canonical Property</span></span>

  
  
<span data-ttu-id="a5f2d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a5f2d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a5f2d-105">消息的 URL 组件名称。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-105">The URL component name for a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a5f2d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a5f2d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a5f2d-107">PR_URL_COMP_NAME，PR_URL_COMP_NAME_A，PR_URL_COMP_NAME_W</span><span class="sxs-lookup"><span data-stu-id="a5f2d-107">PR_URL_COMP_NAME, PR_URL_COMP_NAME_A, PR_URL_COMP_NAME_W</span></span>  <br/> |
|<span data-ttu-id="a5f2d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a5f2d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a5f2d-109">0x10F3</span><span class="sxs-lookup"><span data-stu-id="a5f2d-109">0x10F3</span></span>  <br/> |
|<span data-ttu-id="a5f2d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a5f2d-110">Data type:</span></span>  <br/> |<span data-ttu-id="a5f2d-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a5f2d-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a5f2d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a5f2d-112">Area:</span></span>  <br/> |<span data-ttu-id="a5f2d-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="a5f2d-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a5f2d-114">说明</span><span class="sxs-lookup"><span data-stu-id="a5f2d-114">Remarks</span></span>

<span data-ttu-id="a5f2d-115">这些属性应该是唯一的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-115">These properties should be unique within a folder.</span></span> <span data-ttu-id="a5f2d-116">如果，未设置创建邮件时，消息存储应设置这些属性根据不同的消息属性，具体取决于邮件类。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-116">If not set when the message is created, the message store should set these properties based on various message properties, depending on the message class.</span></span> <span data-ttu-id="a5f2d-117">例如， **IPM。注意**和**IPM。约会**邮件应将此属性设置取决于**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性和**IPM。联系人**邮件应该会根据**dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 属性设置该属性。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-117">For example, the **IPM.Note** and **IPM.Appointment** messages should have this property set based on the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property and the **IPM.Contact** messages should have this property set based on the **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) property.</span></span> <span data-ttu-id="a5f2d-118">对于大多数其他邮件类，此属性应基于**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-118">For most other message classes, this property should be based on the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a5f2d-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="a5f2d-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a5f2d-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="a5f2d-120">Protocol specifications</span></span>

<span data-ttu-id="a5f2d-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a5f2d-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a5f2d-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a5f2d-123">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a5f2d-123">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a5f2d-124">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-124">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="a5f2d-125">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a5f2d-125">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a5f2d-126">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-126">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a5f2d-127">头文件</span><span class="sxs-lookup"><span data-stu-id="a5f2d-127">Header files</span></span>

<span data-ttu-id="a5f2d-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a5f2d-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="a5f2d-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="a5f2d-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a5f2d-130">Mapitags.h</span></span>
  
> <span data-ttu-id="a5f2d-131">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a5f2d-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a5f2d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5f2d-132">See also</span></span>



[<span data-ttu-id="a5f2d-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a5f2d-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a5f2d-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a5f2d-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a5f2d-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a5f2d-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a5f2d-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a5f2d-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

