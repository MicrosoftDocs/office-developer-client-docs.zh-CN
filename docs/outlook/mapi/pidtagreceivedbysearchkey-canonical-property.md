---
title: PidTagReceivedBySearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedBySearchKey
api_type:
- COM
ms.assetid: 4b37555a-1d07-4f42-95e3-b8fa37ed0c3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bace518784bf24807cfca09032a4f3912f4e98ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359204"
---
# <a name="pidtagreceivedbysearchkey-canonical-property"></a><span data-ttu-id="eec48-103">PidTagReceivedBySearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="eec48-103">PidTagReceivedBySearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="eec48-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eec48-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eec48-105">包含接收邮件的邮件传递用户的搜索密钥。</span><span class="sxs-lookup"><span data-stu-id="eec48-105">Contains the search key of the messaging user who receives the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eec48-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="eec48-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="eec48-107">PR_RECEIVED_BY_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="eec48-107">PR_RECEIVED_BY_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="eec48-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="eec48-108">Identifier:</span></span>  <br/> |<span data-ttu-id="eec48-109">0x0051</span><span class="sxs-lookup"><span data-stu-id="eec48-109">0x0051</span></span>  <br/> |
|<span data-ttu-id="eec48-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="eec48-110">Data type:</span></span>  <br/> |<span data-ttu-id="eec48-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="eec48-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="eec48-112">区域：</span><span class="sxs-lookup"><span data-stu-id="eec48-112">Area:</span></span>  <br/> |<span data-ttu-id="eec48-113">地址</span><span class="sxs-lookup"><span data-stu-id="eec48-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eec48-114">备注</span><span class="sxs-lookup"><span data-stu-id="eec48-114">Remarks</span></span>

<span data-ttu-id="eec48-115">此属性是接收邮件的邮件用户的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="eec48-115">This property is one of the address properties for the messaging user who receives the message.</span></span> <span data-ttu-id="eec48-116">必须由传入传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="eec48-116">It must be set by the incoming transport provider.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="eec48-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="eec48-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="eec48-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="eec48-118">Protocol specifications</span></span>

<span data-ttu-id="eec48-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eec48-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eec48-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="eec48-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="eec48-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eec48-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eec48-122">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="eec48-122">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="eec48-123">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eec48-123">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eec48-124">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="eec48-124">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="eec48-125">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eec48-125">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eec48-126">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="eec48-126">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="eec48-127">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eec48-127">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eec48-128">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="eec48-128">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="eec48-129">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eec48-129">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eec48-130">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="eec48-130">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="eec48-131">头文件</span><span class="sxs-lookup"><span data-stu-id="eec48-131">Header files</span></span>

<span data-ttu-id="eec48-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="eec48-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="eec48-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="eec48-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="eec48-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="eec48-134">Mapitags.h</span></span>
  
> <span data-ttu-id="eec48-135">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="eec48-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eec48-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eec48-136">See also</span></span>



[<span data-ttu-id="eec48-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="eec48-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="eec48-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="eec48-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="eec48-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="eec48-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="eec48-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="eec48-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

