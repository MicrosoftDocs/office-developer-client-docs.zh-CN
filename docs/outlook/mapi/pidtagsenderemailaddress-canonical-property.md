---
title: PidTagSenderEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSenderEmailAddress
api_type:
- COM
ms.assetid: 6e1531ac-489b-4224-921a-8fd13ace9497
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b97446c946c31ca8b55ce6c412814b48f4ee363c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778369"
---
# <a name="pidtagsenderemailaddress-canonical-property"></a><span data-ttu-id="15555-103">PidTagSenderEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="15555-103">PidTagSenderEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="15555-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="15555-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="15555-105">包含邮件发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="15555-105">Contains the message sender's email address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="15555-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="15555-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="15555-107">PR_SENDER_EMAIL_ADDRESS，PR_SENDER_EMAIL_ADDRESS_A，PR_SENDER_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="15555-107">PR_SENDER_EMAIL_ADDRESS, PR_SENDER_EMAIL_ADDRESS_A, PR_SENDER_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="15555-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="15555-108">Identifier:</span></span>  <br/> |<span data-ttu-id="15555-109">0x0C1F</span><span class="sxs-lookup"><span data-stu-id="15555-109">0x0C1F</span></span>  <br/> |
|<span data-ttu-id="15555-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="15555-110">Data type:</span></span>  <br/> |<span data-ttu-id="15555-111">PT_UNICOIDE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="15555-111">PT_UNICOIDE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="15555-112">区域：</span><span class="sxs-lookup"><span data-stu-id="15555-112">Area:</span></span>  <br/> |<span data-ttu-id="15555-113">Address</span><span class="sxs-lookup"><span data-stu-id="15555-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="15555-114">备注</span><span class="sxs-lookup"><span data-stu-id="15555-114">Remarks</span></span>

<span data-ttu-id="15555-115">这些属性是发件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="15555-115">These properties are examples of the address properties for the message sender.</span></span> <span data-ttu-id="15555-116">传出的传输提供程序，应永远不会传播任何以前现有值，必须设置它们。</span><span class="sxs-lookup"><span data-stu-id="15555-116">They must be set by the outgoing transport provider, which should never propagate any previously existing values.</span></span>
  
<span data-ttu-id="15555-117">如果没有传输提供程序具有提供任何发件人地址属性，MAPI 后台处理程序尝试填写通过调用[IMAPISession::QueryIdentity](imapisession-queryidentity.md)方法的项标识符。</span><span class="sxs-lookup"><span data-stu-id="15555-117">If no transport provider has supplied any sender address properties, the MAPI spooler attempts to fill them in by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method for an entry identifier.</span></span> <span data-ttu-id="15555-118">如果不提供了任何条目标识符，MAPI 后台处理程序中所有发件人地址类型的属性的 PT_TSTRING 存储"Unknown"。</span><span class="sxs-lookup"><span data-stu-id="15555-118">If no entry identifiers have been provided, the MAPI spooler stores "Unknown" in all the sender address properties of type PT_TSTRING.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="15555-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="15555-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="15555-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="15555-120">Protocol specifications</span></span>

<span data-ttu-id="15555-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="15555-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="15555-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-124">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="15555-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="15555-125">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-125">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-126">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="15555-126">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="15555-127">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-127">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-128">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="15555-128">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="15555-129">[[MS OXOPOST]](http://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-129">[[MS-OXOPOST]](http://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-130">指定的属性和允许的操作的 post 对象。</span><span class="sxs-lookup"><span data-stu-id="15555-130">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="15555-131">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-131">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-132">指定的属性和允许的联系人和个人通讯组列表对象的操作。</span><span class="sxs-lookup"><span data-stu-id="15555-132">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
<span data-ttu-id="15555-133">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="15555-133">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="15555-134">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="15555-134">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="15555-135">头文件</span><span class="sxs-lookup"><span data-stu-id="15555-135">Header files</span></span>

<span data-ttu-id="15555-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="15555-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="15555-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="15555-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="15555-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="15555-138">Mapitags.h</span></span>
  
> <span data-ttu-id="15555-139">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="15555-139">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15555-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15555-140">See also</span></span>



[<span data-ttu-id="15555-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="15555-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="15555-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="15555-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="15555-143">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="15555-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="15555-144">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="15555-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

