---
title: PidTagSenderName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSenderName
api_type:
- COM
ms.assetid: 33fb53a8-4c7b-4418-8849-b6f9a1580172
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 953e792b6d18f7da9ee7eb17e07e6e05557e98ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355067"
---
# <a name="pidtagsendername-canonical-property"></a><span data-ttu-id="2c152-103">PidTagSenderName 规范属性</span><span class="sxs-lookup"><span data-stu-id="2c152-103">PidTagSenderName Canonical Property</span></span>

  
  
<span data-ttu-id="2c152-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c152-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c152-105">包含邮件发件人的邮件显示名称。</span><span class="sxs-lookup"><span data-stu-id="2c152-105">Contains the message sender's display name.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2c152-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2c152-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2c152-107">PR_SENDER_NAME、PR_SENDER_NAME_A、PR_SENDER_NAME_W</span><span class="sxs-lookup"><span data-stu-id="2c152-107">PR_SENDER_NAME, PR_SENDER_NAME_A, PR_SENDER_NAME_W</span></span>  <br/> |
|<span data-ttu-id="2c152-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2c152-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2c152-109">0x0C1A</span><span class="sxs-lookup"><span data-stu-id="2c152-109">0x0C1A</span></span>  <br/> |
|<span data-ttu-id="2c152-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2c152-110">Data type:</span></span>  <br/> |<span data-ttu-id="2c152-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="2c152-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="2c152-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2c152-112">Area:</span></span>  <br/> |<span data-ttu-id="2c152-113">地址</span><span class="sxs-lookup"><span data-stu-id="2c152-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2c152-114">备注</span><span class="sxs-lookup"><span data-stu-id="2c152-114">Remarks</span></span>

<span data-ttu-id="2c152-115">这些属性是邮件发件人的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="2c152-115">These properties are examples of the address properties for the message sender.</span></span> <span data-ttu-id="2c152-116">它必须由传出传输提供程序设置，该传输提供程序不得传播任何以前存在的值。</span><span class="sxs-lookup"><span data-stu-id="2c152-116">It must be set by the outgoing transport provider, which should never propagate any previously existing values.</span></span>
  
<span data-ttu-id="2c152-117">如果没有传输提供程序提供任何发件人地址属性，MAPI 后台处理程序将尝试通过调用条目标识符的 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md) 方法来填充这些属性。</span><span class="sxs-lookup"><span data-stu-id="2c152-117">If no transport provider has supplied any sender address properties, the MAPI spooler attempts to fill them in by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method for an entry identifier.</span></span> <span data-ttu-id="2c152-118">如果未提供条目标识符，MAPI 后台处理程序将"Unknown"存储在类型为 PT_TSTRING 的所有发件人地址属性中。</span><span class="sxs-lookup"><span data-stu-id="2c152-118">If no entry identifiers have been provided, the MAPI spooler stores "Unknown" in all the sender address properties of type PT_TSTRING.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2c152-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2c152-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2c152-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="2c152-120">Protocol specifications</span></span>

<span data-ttu-id="2c152-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="2c152-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2c152-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-124">描述用于发送与客户端上的共享文件夹有关的信息的邮件的格式。</span><span class="sxs-lookup"><span data-stu-id="2c152-124">Describes the format of messages used to send information related to sharing folders on the client.</span></span>
    
<span data-ttu-id="2c152-125">[[MS-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-125">[[MS-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-126">指定表示 RSS 项目的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2c152-126">Specifies the properties and operations that represent RSS items.</span></span>
    
<span data-ttu-id="2c152-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-128">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="2c152-128">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="2c152-129">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-129">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-130">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="2c152-130">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="2c152-131">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-131">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-132">指定 post 对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2c152-132">Specifies the properties and operations that are permissible for post objects.</span></span>
    
<span data-ttu-id="2c152-133">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-133">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-134">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2c152-134">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="2c152-135">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2c152-135">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2c152-136">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="2c152-136">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2c152-137">头文件</span><span class="sxs-lookup"><span data-stu-id="2c152-137">Header files</span></span>

<span data-ttu-id="2c152-138">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2c152-138">Mapidefs.h</span></span>
  
> <span data-ttu-id="2c152-139">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2c152-139">Provides data type definitions.</span></span>
    
<span data-ttu-id="2c152-140">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2c152-140">Mapitags.h</span></span>
  
> <span data-ttu-id="2c152-141">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2c152-141">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2c152-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c152-142">See also</span></span>



[<span data-ttu-id="2c152-143">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2c152-143">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2c152-144">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2c152-144">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2c152-145">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2c152-145">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2c152-146">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2c152-146">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

