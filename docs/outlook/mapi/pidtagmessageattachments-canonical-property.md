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
# <a name="pidtagmessageattachments-canonical-property"></a><span data-ttu-id="e557e-103">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="e557e-103">PidTagMessageAttachments Canonical Property</span></span>

  
  
<span data-ttu-id="e557e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e557e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e557e-105">包含邮件附件的表。</span><span class="sxs-lookup"><span data-stu-id="e557e-105">Contains a table of attachments for a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e557e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e557e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e557e-107">PR_MESSAGE_ATTACHMENTS</span><span class="sxs-lookup"><span data-stu-id="e557e-107">PR_MESSAGE_ATTACHMENTS</span></span>  <br/> |
|<span data-ttu-id="e557e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e557e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e557e-109">0x0E13</span><span class="sxs-lookup"><span data-stu-id="e557e-109">0x0E13</span></span>  <br/> |
|<span data-ttu-id="e557e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e557e-110">Data type:</span></span>  <br/> |<span data-ttu-id="e557e-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="e557e-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="e557e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e557e-112">Area:</span></span>  <br/> |<span data-ttu-id="e557e-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="e557e-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e557e-114">注解</span><span class="sxs-lookup"><span data-stu-id="e557e-114">Remarks</span></span>

<span data-ttu-id="e557e-115">此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。</span><span class="sxs-lookup"><span data-stu-id="e557e-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="e557e-116">作为 PT_OBJECT 类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它。</span><span class="sxs-lookup"><span data-stu-id="e557e-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="e557e-117">其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求**IID_IMAPITable**接口标识符。</span><span class="sxs-lookup"><span data-stu-id="e557e-117">Its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the **IID_IMAPITable** interface identifier.</span></span> <span data-ttu-id="e557e-118">如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可能需要报告它。</span><span class="sxs-lookup"><span data-stu-id="e557e-118">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but may optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="e557e-119">若要检索表内容, 客户端应用程序应调用[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e557e-119">To retrieve table contents, a client application should call the [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) method.</span></span> <span data-ttu-id="e557e-120">有关详细信息, 请参阅[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="e557e-120">For more information, see [Attachment Tables](attachment-tables.md).</span></span> 
  
<span data-ttu-id="e557e-121">此属性可用于通过在[SSubRestriction](ssubrestriction.md)结构中指定子属性的限制。</span><span class="sxs-lookup"><span data-stu-id="e557e-121">This property can be used for subobject restriction by specifying it in the [SSubRestriction](ssubrestriction.md) structure.</span></span> <span data-ttu-id="e557e-122">这样, 客户端就可以将容器的视图限制为包含符合给定条件的附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="e557e-122">This allows the client to limit the view of a container to messages with attachments meeting given criteria.</span></span> <span data-ttu-id="e557e-123">如果 "附件" 表中至少有一行 (即一个附件) 满足子控件限制, 则会有一条消息符合查看条件。</span><span class="sxs-lookup"><span data-stu-id="e557e-123">A message qualifies for viewing if at least one row in its attachments table, that is, one attachment, satisfies the subobject restriction.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e557e-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="e557e-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e557e-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="e557e-125">Protocol specifications</span></span>

<span data-ttu-id="e557e-126">[[毫秒-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e557e-126">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e557e-127">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="e557e-127">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="e557e-128">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e557e-128">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e557e-129">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="e557e-129">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="e557e-130">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e557e-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e557e-131">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="e557e-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e557e-132">头文件</span><span class="sxs-lookup"><span data-stu-id="e557e-132">Header files</span></span>

<span data-ttu-id="e557e-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e557e-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="e557e-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e557e-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="e557e-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e557e-135">Mapitags.h</span></span>
  
> <span data-ttu-id="e557e-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e557e-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e557e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e557e-137">See also</span></span>



[<span data-ttu-id="e557e-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e557e-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e557e-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e557e-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e557e-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e557e-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e557e-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e557e-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

