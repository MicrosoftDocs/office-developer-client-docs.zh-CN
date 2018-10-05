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
ms.openlocfilehash: 5f13c2825fc0127b95fbf5bc0b41d68c64556864
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384085"
---
# <a name="pidtagmessageattachments-canonical-property"></a><span data-ttu-id="5aac1-103">PidTagMessageAttachments 规范属性</span><span class="sxs-lookup"><span data-stu-id="5aac1-103">PidTagMessageAttachments Canonical Property</span></span>

  
  
<span data-ttu-id="5aac1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5aac1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5aac1-105">包含可应用到内容表中查找包含满足限制的附件子对象的所有消息的限制的表。</span><span class="sxs-lookup"><span data-stu-id="5aac1-105">Contains a table of restrictions that can be applied to a contents table to find all messages that contain attachment subobjects that meet the restrictions.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5aac1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5aac1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5aac1-107">PR_MESSAGE_ATTACHMENTS</span><span class="sxs-lookup"><span data-stu-id="5aac1-107">PR_MESSAGE_ATTACHMENTS</span></span>  <br/> |
|<span data-ttu-id="5aac1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5aac1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5aac1-109">0x0E13</span><span class="sxs-lookup"><span data-stu-id="5aac1-109">0x0E13</span></span>  <br/> |
|<span data-ttu-id="5aac1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5aac1-110">Data type:</span></span>  <br/> |<span data-ttu-id="5aac1-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="5aac1-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="5aac1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5aac1-112">Area:</span></span>  <br/> |<span data-ttu-id="5aac1-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="5aac1-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5aac1-114">说明</span><span class="sxs-lookup"><span data-stu-id="5aac1-114">Remarks</span></span>

<span data-ttu-id="5aac1-115">可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。</span><span class="sxs-lookup"><span data-stu-id="5aac1-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="5aac1-116">作为 PT_OBJECT 类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5aac1-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="5aac1-117">应由请求**IID_IMAPITable**接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。</span><span class="sxs-lookup"><span data-stu-id="5aac1-117">Its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the **IID_IMAPITable** interface identifier.</span></span> <span data-ttu-id="5aac1-118">服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法如果设置，但可以选择将其报告或不如果它未设置。</span><span class="sxs-lookup"><span data-stu-id="5aac1-118">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but may optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="5aac1-119">若要检索目录，客户端应用程序应调用[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5aac1-119">To retrieve table contents, a client application should call the [IMessage::GetAttachmentTable](imessage-getattachmenttable.md) method.</span></span> <span data-ttu-id="5aac1-120">有关详细信息，请参阅[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5aac1-120">For more information, see [Attachment Tables](attachment-tables.md).</span></span> 
  
<span data-ttu-id="5aac1-121">此属性可用于任务的子对象限制通过指定[SSubRestriction](ssubrestriction.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="5aac1-121">This property can be used for subobject restriction by specifying it in the [SSubRestriction](ssubrestriction.md) structure.</span></span> <span data-ttu-id="5aac1-122">这样，客户端限制容器与给定条件的邮件的附件为会议的视图。</span><span class="sxs-lookup"><span data-stu-id="5aac1-122">This allows the client to limit the view of a container to messages with attachments meeting given criteria.</span></span> <span data-ttu-id="5aac1-123">查看如果其附件表，即一个附件中的至少一个行满足子对象限制符合一条消息。</span><span class="sxs-lookup"><span data-stu-id="5aac1-123">A message qualifies for viewing if at least one row in its attachments table, that is, one attachment, satisfies the subobject restriction.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5aac1-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="5aac1-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5aac1-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="5aac1-125">Protocol specifications</span></span>

<span data-ttu-id="5aac1-126">[[MS OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5aac1-126">[[MS-OXCDATA]](https://msdn.microsoft.com/library/1afa0cd9-b1a0-4520-b623-bf15030af5d8%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5aac1-127">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="5aac1-127">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="5aac1-128">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5aac1-128">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5aac1-129">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="5aac1-129">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="5aac1-130">[[MS OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5aac1-130">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5aac1-131">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="5aac1-131">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5aac1-132">头文件</span><span class="sxs-lookup"><span data-stu-id="5aac1-132">Header files</span></span>

<span data-ttu-id="5aac1-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5aac1-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="5aac1-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5aac1-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="5aac1-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5aac1-135">Mapitags.h</span></span>
  
> <span data-ttu-id="5aac1-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5aac1-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5aac1-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5aac1-137">See also</span></span>



[<span data-ttu-id="5aac1-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5aac1-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5aac1-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5aac1-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5aac1-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5aac1-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5aac1-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5aac1-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

