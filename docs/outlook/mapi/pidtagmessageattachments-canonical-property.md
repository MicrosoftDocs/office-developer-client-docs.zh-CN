---
title: PidTagMessageAttachments 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageAttachments
api_type:
- HeaderDef
ms.assetid: 85762771-b823-4227-9a7b-75b6ac280b2d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 975f52e6ea0ca7a469a027565f845f9dc0f9c2cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342565"
---
# <a name="pidtagmessageattachments-canonical-property"></a><span data-ttu-id="d89f3-103">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="d89f3-103">PidTagMessageAttachments Canonical Property</span></span>

  
  
<span data-ttu-id="d89f3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d89f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d89f3-105">包含邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="d89f3-105">Contains a table of attachments for a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d89f3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d89f3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d89f3-107">PR_MESSAGE_ATTACHMENTS</span><span class="sxs-lookup"><span data-stu-id="d89f3-107">PR_MESSAGE_ATTACHMENTS</span></span>  <br/> |
|<span data-ttu-id="d89f3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d89f3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d89f3-109">0x0E13</span><span class="sxs-lookup"><span data-stu-id="d89f3-109">0x0E13</span></span>  <br/> |
|<span data-ttu-id="d89f3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d89f3-110">Data type:</span></span>  <br/> |<span data-ttu-id="d89f3-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="d89f3-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="d89f3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d89f3-112">Area:</span></span>  <br/> |<span data-ttu-id="d89f3-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="d89f3-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d89f3-114">备注</span><span class="sxs-lookup"><span data-stu-id="d89f3-114">Remarks</span></span>

<span data-ttu-id="d89f3-115">此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。</span><span class="sxs-lookup"><span data-stu-id="d89f3-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="d89f3-116">作为类型为 [PT_OBJECT，IMAPIProp：：GetProps](imapiprop-getprops.md) 方法无法成功检索它。</span><span class="sxs-lookup"><span data-stu-id="d89f3-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="d89f3-117">它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法访问，并请求 **IID_IMAPITable标识符。**</span><span class="sxs-lookup"><span data-stu-id="d89f3-117">Its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the **IID_IMAPITable** interface identifier.</span></span> <span data-ttu-id="d89f3-118">如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但如果尚未设置，也可以不报告此方法。</span><span class="sxs-lookup"><span data-stu-id="d89f3-118">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but may optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="d89f3-119">若要检索表内容，客户端应用程序应调用 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d89f3-119">To retrieve table contents, a client application should call the [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) method.</span></span> <span data-ttu-id="d89f3-120">有关详细信息，请参阅附件 [表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d89f3-120">For more information, see [Attachment Tables](attachment-tables.md).</span></span> 
  
<span data-ttu-id="d89f3-121">此属性可用于子对象限制，具体方法为在 [SSubRestriction](ssubrestriction.md) 结构中指定它。</span><span class="sxs-lookup"><span data-stu-id="d89f3-121">This property can be used for subobject restriction by specifying it in the [SSubRestriction](ssubrestriction.md) structure.</span></span> <span data-ttu-id="d89f3-122">这允许客户端将容器视图限制为附件符合给定条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="d89f3-122">This allows the client to limit the view of a container to messages with attachments meeting given criteria.</span></span> <span data-ttu-id="d89f3-123">如果附件表中至少有一行（即一个附件）满足子对象限制，则邮件符合查看条件。</span><span class="sxs-lookup"><span data-stu-id="d89f3-123">A message qualifies for viewing if at least one row in its attachments table, that is, one attachment, satisfies the subobject restriction.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d89f3-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="d89f3-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d89f3-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="d89f3-125">Protocol specifications</span></span>

<span data-ttu-id="d89f3-126">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d89f3-126">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d89f3-127">定义远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="d89f3-127">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="d89f3-128">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d89f3-128">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d89f3-129">定义远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="d89f3-129">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="d89f3-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d89f3-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d89f3-131">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="d89f3-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d89f3-132">头文件</span><span class="sxs-lookup"><span data-stu-id="d89f3-132">Header files</span></span>

<span data-ttu-id="d89f3-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d89f3-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="d89f3-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d89f3-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="d89f3-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d89f3-135">Mapitags.h</span></span>
  
> <span data-ttu-id="d89f3-136">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d89f3-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d89f3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d89f3-137">See also</span></span>



[<span data-ttu-id="d89f3-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d89f3-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d89f3-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d89f3-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d89f3-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d89f3-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d89f3-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d89f3-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

