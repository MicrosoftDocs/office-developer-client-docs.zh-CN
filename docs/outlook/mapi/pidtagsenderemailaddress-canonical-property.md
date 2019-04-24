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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 82c0e386ab9231d1066dbdc4456c31031d2409c1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359162"
---
# <a name="pidtagsenderemailaddress-canonical-property"></a><span data-ttu-id="c4637-103">PidTagSenderEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="c4637-103">PidTagSenderEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="c4637-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4637-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4637-105">包含邮件发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c4637-105">Contains the message sender's email address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4637-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c4637-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c4637-107">PR_SENDER_EMAIL_ADDRESS、PR_SENDER_EMAIL_ADDRESS_A、PR_SENDER_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="c4637-107">PR_SENDER_EMAIL_ADDRESS, PR_SENDER_EMAIL_ADDRESS_A, PR_SENDER_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="c4637-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c4637-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c4637-109">0x0C1F</span><span class="sxs-lookup"><span data-stu-id="c4637-109">0x0C1F</span></span>  <br/> |
|<span data-ttu-id="c4637-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c4637-110">Data type:</span></span>  <br/> |<span data-ttu-id="c4637-111">PT_UNICOIDE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="c4637-111">PT_UNICOIDE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="c4637-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c4637-112">Area:</span></span>  <br/> |<span data-ttu-id="c4637-113">Address</span><span class="sxs-lookup"><span data-stu-id="c4637-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c4637-114">注解</span><span class="sxs-lookup"><span data-stu-id="c4637-114">Remarks</span></span>

<span data-ttu-id="c4637-115">这些属性是邮件发件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="c4637-115">These properties are examples of the address properties for the message sender.</span></span> <span data-ttu-id="c4637-116">它们必须由传出传输提供程序设置, 该提供程序决不会传播任何以前存在的值。</span><span class="sxs-lookup"><span data-stu-id="c4637-116">They must be set by the outgoing transport provider, which should never propagate any previously existing values.</span></span>
  
<span data-ttu-id="c4637-117">如果没有任何传输提供程序提供任何发件人地址属性, MAPI 后台处理程序将尝试通过调用条目标识符的[IMAPISession:: QueryIdentity](imapisession-queryidentity.md)方法来填充这些属性。</span><span class="sxs-lookup"><span data-stu-id="c4637-117">If no transport provider has supplied any sender address properties, the MAPI spooler attempts to fill them in by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method for an entry identifier.</span></span> <span data-ttu-id="c4637-118">如果未提供条目标识符, MAPI 后台处理程序会在类型 PT_TSTRING 的所有发件人地址属性中存储 "Unknown"。</span><span class="sxs-lookup"><span data-stu-id="c4637-118">If no entry identifiers have been provided, the MAPI spooler stores "Unknown" in all the sender address properties of type PT_TSTRING.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c4637-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="c4637-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c4637-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="c4637-120">Protocol specifications</span></span>

<span data-ttu-id="c4637-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c4637-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c4637-123">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-124">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c4637-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="c4637-125">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-125">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-126">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="c4637-126">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="c4637-127">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-127">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-128">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="c4637-128">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="c4637-129">[[毫秒-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-129">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-130">指定允许用于 post 对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c4637-130">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="c4637-131">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-131">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-132">指定允许用于联系人和个人通讯组列表对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c4637-132">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
<span data-ttu-id="c4637-133">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4637-133">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c4637-134">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="c4637-134">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c4637-135">头文件</span><span class="sxs-lookup"><span data-stu-id="c4637-135">Header files</span></span>

<span data-ttu-id="c4637-136">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c4637-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="c4637-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c4637-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="c4637-138">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c4637-138">Mapitags.h</span></span>
  
> <span data-ttu-id="c4637-139">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c4637-139">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c4637-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4637-140">See also</span></span>



[<span data-ttu-id="c4637-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c4637-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c4637-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c4637-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c4637-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c4637-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c4637-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c4637-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

