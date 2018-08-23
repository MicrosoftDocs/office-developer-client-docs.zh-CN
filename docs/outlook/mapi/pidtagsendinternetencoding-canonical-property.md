---
title: PidTagSendInternetEncoding 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSendInternetEncoding
api_type:
- COM
ms.assetid: ae408b4f-dee3-484b-a19c-f472cfa95996
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33b9931a269eb4b5ee0429287d60fa1962b0e4f2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584231"
---
# <a name="pidtagsendinternetencoding-canonical-property"></a><span data-ttu-id="00828-103">PidTagSendInternetEncoding 规范属性</span><span class="sxs-lookup"><span data-stu-id="00828-103">PidTagSendInternetEncoding Canonical Property</span></span>

  
  
<span data-ttu-id="00828-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00828-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00828-105">包含编码首选项的位掩码。</span><span class="sxs-lookup"><span data-stu-id="00828-105">Contains a bitmask of encoding preferences.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="00828-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="00828-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="00828-107">PR_SEND_INTERNET_ENCODING</span><span class="sxs-lookup"><span data-stu-id="00828-107">PR_SEND_INTERNET_ENCODING</span></span>  <br/> |
|<span data-ttu-id="00828-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="00828-108">Identifier:</span></span>  <br/> |<span data-ttu-id="00828-109">0x3A71</span><span class="sxs-lookup"><span data-stu-id="00828-109">0x3A71</span></span>  <br/> |
|<span data-ttu-id="00828-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="00828-110">Data type:</span></span>  <br/> |<span data-ttu-id="00828-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="00828-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="00828-112">区域：</span><span class="sxs-lookup"><span data-stu-id="00828-112">Area:</span></span>  <br/> |<span data-ttu-id="00828-113">Address</span><span class="sxs-lookup"><span data-stu-id="00828-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="00828-114">注解</span><span class="sxs-lookup"><span data-stu-id="00828-114">Remarks</span></span>

<span data-ttu-id="00828-115">设置此属性来指示使用的编码选项。</span><span class="sxs-lookup"><span data-stu-id="00828-115">Set this property to indicate the encoding options used.</span></span> 
  
<span data-ttu-id="00828-116">此属性包含以下标志：</span><span class="sxs-lookup"><span data-stu-id="00828-116">This property contains the following flags:</span></span>
  
<span data-ttu-id="00828-117">BODY_ENCODING_HTML</span><span class="sxs-lookup"><span data-stu-id="00828-117">BODY_ENCODING_HTML</span></span> 
  
> <span data-ttu-id="00828-118">HTML 格式的消息文本进行编码。</span><span class="sxs-lookup"><span data-stu-id="00828-118">Encode the message text in HTML.</span></span> <span data-ttu-id="00828-119">除非设置了 ENCODING_MIME 标志，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="00828-119">This flag is ignored unless the ENCODING_MIME flag is set.</span></span> 
    
<span data-ttu-id="00828-120">BODY_ENCODING_TEXT_AND_HTML</span><span class="sxs-lookup"><span data-stu-id="00828-120">BODY_ENCODING_TEXT_AND_HTML</span></span> 
  
> <span data-ttu-id="00828-121">编码为多用途 Internet 邮件扩展 (MIME) 的替代方案中使用的文本和 HTML 的消息文本。</span><span class="sxs-lookup"><span data-stu-id="00828-121">Encode the message text using text and HTML as Multipurpose Internet Mail Extensions (MIME) multipart alternatives.</span></span> <span data-ttu-id="00828-122">除非设置了 ENCODING_MIME 标志，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="00828-122">This flag is ignored unless the ENCODING_MIME flag is set.</span></span> 
    
<span data-ttu-id="00828-123">ENCODING_MIME</span><span class="sxs-lookup"><span data-stu-id="00828-123">ENCODING_MIME</span></span> 
  
> <span data-ttu-id="00828-124">编码使用 MIME 邮件。</span><span class="sxs-lookup"><span data-stu-id="00828-124">Encode the message using MIME.</span></span> <span data-ttu-id="00828-125">如果未设置此标志，MAPI 对采用纯文本形式的消息文本和 UUENCODE 中的附件进行编码。</span><span class="sxs-lookup"><span data-stu-id="00828-125">If this flag is not set, MAPI encodes the message text in plain text and the attachments in UUENCODE.</span></span> 
    
<span data-ttu-id="00828-126">ENCODING_PREFERENCE</span><span class="sxs-lookup"><span data-stu-id="00828-126">ENCODING_PREFERENCE</span></span> 
  
> <span data-ttu-id="00828-127">使用此位掩码中其他标志来确定编码。</span><span class="sxs-lookup"><span data-stu-id="00828-127">Use the other flags in this bitmask to determine the encoding.</span></span> <span data-ttu-id="00828-128">如果未设置此标志，MAPI 使其消息的系统进行编码的决策。</span><span class="sxs-lookup"><span data-stu-id="00828-128">If this flag is not set, MAPI leaves it to the messaging system to make encoding decisions.</span></span> 
    
<span data-ttu-id="00828-129">MAC_ATTACH_ENCODING_APPLEDOUBLE</span><span class="sxs-lookup"><span data-stu-id="00828-129">MAC_ATTACH_ENCODING_APPLEDOUBLE</span></span> 
  
> <span data-ttu-id="00828-130">对在 Apple 双模式下的 Macintosh 附件进行编码。</span><span class="sxs-lookup"><span data-stu-id="00828-130">Encode Macintosh attachments in Apple double mode.</span></span> <span data-ttu-id="00828-131">除非设置了 ENCODING_MIME 标志，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="00828-131">This flag is ignored unless the ENCODING_MIME flag is set.</span></span> 
    
<span data-ttu-id="00828-132">MAC_ATTACH_ENCODING_APPLESINGLE</span><span class="sxs-lookup"><span data-stu-id="00828-132">MAC_ATTACH_ENCODING_APPLESINGLE</span></span> 
  
> <span data-ttu-id="00828-133">对在 Apple 单模式 Macintosh 附件进行编码。</span><span class="sxs-lookup"><span data-stu-id="00828-133">Encode Macintosh attachments in Apple single mode.</span></span> <span data-ttu-id="00828-134">除非设置了 ENCODING_MIME 标志，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="00828-134">This flag is ignored unless the ENCODING_MIME flag is set.</span></span> 
    
<span data-ttu-id="00828-135">MAC_ATTACH_ENCODING_UUENCODE</span><span class="sxs-lookup"><span data-stu-id="00828-135">MAC_ATTACH_ENCODING_UUENCODE</span></span> 
  
> <span data-ttu-id="00828-136">对在 UUENCODE Macintosh 附件进行编码。</span><span class="sxs-lookup"><span data-stu-id="00828-136">Encode Macintosh attachments in UUENCODE.</span></span> <span data-ttu-id="00828-137">如果设置了 ENCODING_MIME 标志，则忽略此标志并 BinHex 编码改为使用。</span><span class="sxs-lookup"><span data-stu-id="00828-137">If the ENCODING_MIME flag is set, this flag is ignored and BinHex encoding is used instead.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="00828-138">相关资源</span><span class="sxs-lookup"><span data-stu-id="00828-138">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="00828-139">协议规范</span><span class="sxs-lookup"><span data-stu-id="00828-139">Protocol specifications</span></span>

<span data-ttu-id="00828-140">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="00828-140">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="00828-141">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="00828-141">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="00828-142">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="00828-142">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="00828-143">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="00828-143">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="00828-144">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="00828-144">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="00828-145">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="00828-145">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="00828-146">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="00828-146">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="00828-147">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="00828-147">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="00828-148">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="00828-148">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="00828-149">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="00828-149">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="00828-150">头文件</span><span class="sxs-lookup"><span data-stu-id="00828-150">Header files</span></span>

<span data-ttu-id="00828-151">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="00828-151">Mapidefs.h</span></span>
  
> <span data-ttu-id="00828-152">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="00828-152">Provides data type definitions.</span></span>
    
<span data-ttu-id="00828-153">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="00828-153">Mapitags.h</span></span>
  
> <span data-ttu-id="00828-154">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="00828-154">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="00828-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00828-155">See also</span></span>



[<span data-ttu-id="00828-156">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="00828-156">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="00828-157">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="00828-157">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="00828-158">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="00828-158">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="00828-159">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="00828-159">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

