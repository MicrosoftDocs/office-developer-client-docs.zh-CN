---
title: PidTagAttachPayloadClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachPayloadClass
api_type:
- HeaderDef
ms.assetid: bc4de217-8241-45e7-9e97-8f0c1b16691a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cef412d212bf29cfd1a1d5c4b2911440fae6a15e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777366"
---
# <a name="pidtagattachpayloadclass-canonical-property"></a><span data-ttu-id="803b8-103">PidTagAttachPayloadClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="803b8-103">PidTagAttachPayloadClass Canonical Property</span></span>

  
  
<span data-ttu-id="803b8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="803b8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="803b8-105">包含 MIME X 负载类标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="803b8-105">Contains the value of a MIME X-Payload-Class header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="803b8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="803b8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="803b8-107">PR_ATTACH_PAYLOAD_CLASS，PR_ATTACH_PAYLOAD_CLASS_A，PR_ATTACH_PAYLOAD_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="803b8-107">PR_ATTACH_PAYLOAD_CLASS, PR_ATTACH_PAYLOAD_CLASS_A, PR_ATTACH_PAYLOAD_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="803b8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="803b8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="803b8-109">0x371A</span><span class="sxs-lookup"><span data-stu-id="803b8-109">0x371A</span></span>  <br/> |
|<span data-ttu-id="803b8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="803b8-110">Data type:</span></span>  <br/> |<span data-ttu-id="803b8-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="803b8-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="803b8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="803b8-112">Area:</span></span>  <br/> |<span data-ttu-id="803b8-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="803b8-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="803b8-114">说明</span><span class="sxs-lookup"><span data-stu-id="803b8-114">Remarks</span></span>

<span data-ttu-id="803b8-115">若要设置这些属性的值，MIME 客户端应写入负载 X 级标头字段将分析作为附件的 MIME 实体。</span><span class="sxs-lookup"><span data-stu-id="803b8-115">To set the value of these properties, MIME clients should write an X-Payload-Class header field to a MIME entity that will be analyzed as an attachment.</span></span>
  
<span data-ttu-id="803b8-116">MIME 读者必须将此标头字段值复制到相应属性的值。</span><span class="sxs-lookup"><span data-stu-id="803b8-116">MIME readers must copy this header field value to the value of the corresponding property.</span></span> <span data-ttu-id="803b8-117">分析作为邮件或邮件正文中，而不是作为附件的 MIME 实体上出现时，MIME 读者应忽略此标头字段。</span><span class="sxs-lookup"><span data-stu-id="803b8-117">MIME readers should ignore this header field when it appears on a MIME entity that is analyzed as a message or message body, rather than as an attachment.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="803b8-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="803b8-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="803b8-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="803b8-119">Protocol specifications</span></span>

<span data-ttu-id="803b8-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="803b8-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="803b8-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="803b8-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="803b8-122">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="803b8-122">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="803b8-123">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="803b8-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="803b8-124">头文件</span><span class="sxs-lookup"><span data-stu-id="803b8-124">Header files</span></span>

<span data-ttu-id="803b8-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="803b8-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="803b8-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="803b8-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="803b8-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="803b8-127">Mapitags.h</span></span>
  
> <span data-ttu-id="803b8-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="803b8-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="803b8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="803b8-129">See also</span></span>



[<span data-ttu-id="803b8-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="803b8-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="803b8-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="803b8-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="803b8-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="803b8-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="803b8-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="803b8-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

