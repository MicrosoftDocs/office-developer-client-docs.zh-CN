---
title: PidTagSenderEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSenderEntryId
api_type:
- COM
ms.assetid: 9f311dd2-853e-46f7-966a-c2ab7a1fb6c5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 46ccc3c7e07e6920508fea630c96700d39366a35
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778388"
---
# <a name="pidtagsenderentryid-canonical-property"></a><span data-ttu-id="31552-103">PidTagSenderEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="31552-103">PidTagSenderEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="31552-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31552-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31552-105">包含邮件发件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="31552-105">Contains the message sender's entry identifier.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="31552-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="31552-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="31552-107">PR_SENDER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="31552-107">PR_SENDER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="31552-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="31552-108">Identifier:</span></span>  <br/> |<span data-ttu-id="31552-109">0x0C19</span><span class="sxs-lookup"><span data-stu-id="31552-109">0x0C19</span></span>  <br/> |
|<span data-ttu-id="31552-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="31552-110">Data type:</span></span>  <br/> |<span data-ttu-id="31552-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="31552-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="31552-112">区域：</span><span class="sxs-lookup"><span data-stu-id="31552-112">Area:</span></span>  <br/> |<span data-ttu-id="31552-113">Address</span><span class="sxs-lookup"><span data-stu-id="31552-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="31552-114">说明</span><span class="sxs-lookup"><span data-stu-id="31552-114">Remarks</span></span>

<span data-ttu-id="31552-115">此属性是一个发件人的地址属性。</span><span class="sxs-lookup"><span data-stu-id="31552-115">This property is one of the address properties for the message sender.</span></span> <span data-ttu-id="31552-116">它必须由传出的传输提供程序，应永远不会传播任何以前现有值设置。</span><span class="sxs-lookup"><span data-stu-id="31552-116">It must be set by the outgoing transport provider, which should never propagate any previously existing values.</span></span>
  
<span data-ttu-id="31552-117">如果没有传输提供程序具有提供任何发件人地址属性，MAPI 后台处理程序尝试填写通过调用[IMAPISession::QueryIdentity](imapisession-queryidentity.md)方法的项标识符。</span><span class="sxs-lookup"><span data-stu-id="31552-117">If no transport provider has supplied any sender address properties, the MAPI spooler attempts to fill them in by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method for an entry identifier.</span></span> <span data-ttu-id="31552-118">如果提供了标识符，任何项的标识符中此属性对应于"Unknown"的字符串 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="31552-118">If no entry identifiers have been provided, the MAPI spooler an identifier corresponding to the string "Unknown" in this property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="31552-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="31552-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="31552-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="31552-120">Protocol specifications</span></span>

<span data-ttu-id="31552-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="31552-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="31552-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-124">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="31552-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="31552-125">[[MS OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-125">[[MS-OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-126">指定的属性和表示 RSS 项目的操作。</span><span class="sxs-lookup"><span data-stu-id="31552-126">Specifies the properties and operations that represent RSS items.</span></span>
    
<span data-ttu-id="31552-127">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-127">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-128">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="31552-128">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="31552-129">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-129">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-130">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="31552-130">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="31552-131">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-131">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-132">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="31552-132">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="31552-133">[[MS OXOPOST]](http://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31552-133">[[MS-OXOPOST]](http://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31552-134">指定的属性和允许的操作的 post 对象。</span><span class="sxs-lookup"><span data-stu-id="31552-134">Specifies the properties and operations that are permissible for post objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="31552-135">头文件</span><span class="sxs-lookup"><span data-stu-id="31552-135">Header files</span></span>

<span data-ttu-id="31552-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="31552-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="31552-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="31552-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="31552-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="31552-138">Mapitags.h</span></span>
  
> <span data-ttu-id="31552-139">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="31552-139">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="31552-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31552-140">See also</span></span>



[<span data-ttu-id="31552-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="31552-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="31552-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="31552-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="31552-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="31552-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="31552-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="31552-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

