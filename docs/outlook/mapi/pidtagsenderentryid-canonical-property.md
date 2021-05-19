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
ms.openlocfilehash: 0bc8b8bd76d553cc4e12e331e9fe7047ef7aaf4e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358910"
---
# <a name="pidtagsenderentryid-canonical-property"></a><span data-ttu-id="8045c-103">PidTagSenderEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="8045c-103">PidTagSenderEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="8045c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8045c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8045c-105">包含邮件发件人的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8045c-105">Contains the message sender's entry identifier.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8045c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8045c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8045c-107">PR_SENDER_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="8045c-107">PR_SENDER_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="8045c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8045c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8045c-109">0x0C19</span><span class="sxs-lookup"><span data-stu-id="8045c-109">0x0C19</span></span>  <br/> |
|<span data-ttu-id="8045c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8045c-110">Data type:</span></span>  <br/> |<span data-ttu-id="8045c-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8045c-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8045c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8045c-112">Area:</span></span>  <br/> |<span data-ttu-id="8045c-113">地址</span><span class="sxs-lookup"><span data-stu-id="8045c-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8045c-114">备注</span><span class="sxs-lookup"><span data-stu-id="8045c-114">Remarks</span></span>

<span data-ttu-id="8045c-115">此属性是邮件发件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="8045c-115">This property is one of the address properties for the message sender.</span></span> <span data-ttu-id="8045c-116">它必须由传出传输提供程序设置，该传输提供程序不得传播任何以前存在的值。</span><span class="sxs-lookup"><span data-stu-id="8045c-116">It must be set by the outgoing transport provider, which should never propagate any previously existing values.</span></span>
  
<span data-ttu-id="8045c-117">如果没有传输提供程序提供任何发件人地址属性，MAPI 后台处理程序将尝试通过调用条目标识符的 [IMAPISession：：QueryIdentity](imapisession-queryidentity.md) 方法来填充这些属性。</span><span class="sxs-lookup"><span data-stu-id="8045c-117">If no transport provider has supplied any sender address properties, the MAPI spooler attempts to fill them in by calling the [IMAPISession::QueryIdentity](imapisession-queryidentity.md) method for an entry identifier.</span></span> <span data-ttu-id="8045c-118">如果未提供条目标识符，则 MAPI 后台处理程序将后台处理程序一个与此属性中的字符串"Unknown"相对应的标识符。</span><span class="sxs-lookup"><span data-stu-id="8045c-118">If no entry identifiers have been provided, the MAPI spooler an identifier corresponding to the string "Unknown" in this property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8045c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="8045c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8045c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="8045c-120">Protocol specifications</span></span>

<span data-ttu-id="8045c-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="8045c-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8045c-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-124">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8045c-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="8045c-125">[[MS-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-125">[[MS-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-126">指定表示 RSS 项目的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8045c-126">Specifies the properties and operations that represent RSS items.</span></span>
    
<span data-ttu-id="8045c-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-127">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-128">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="8045c-128">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="8045c-129">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-129">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-130">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="8045c-130">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="8045c-131">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-131">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-132">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8045c-132">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="8045c-133">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8045c-133">[[MS-OXOPOST]](https://msdn.microsoft.com/library/9b18fdab-aacd-4d73-9534-be9b6ba2f115%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8045c-134">指定 post 对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8045c-134">Specifies the properties and operations that are permissible for post objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8045c-135">头文件</span><span class="sxs-lookup"><span data-stu-id="8045c-135">Header files</span></span>

<span data-ttu-id="8045c-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8045c-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="8045c-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8045c-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="8045c-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8045c-138">Mapitags.h</span></span>
  
> <span data-ttu-id="8045c-139">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8045c-139">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8045c-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8045c-140">See also</span></span>



[<span data-ttu-id="8045c-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8045c-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8045c-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8045c-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8045c-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8045c-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8045c-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8045c-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

