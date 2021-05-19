---
title: PidTagMessageToMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageToMe
api_type:
- HeaderDef
ms.assetid: aeb0fa71-f471-46c5-ad9c-f8afb3fed533
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96a0b010a8ba26a0c1b0cb409f1aaabb308a1c01
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356194"
---
# <a name="pidtagmessagetome-canonical-property"></a><span data-ttu-id="c25b1-103">PidTagMessageToMe 规范属性</span><span class="sxs-lookup"><span data-stu-id="c25b1-103">PidTagMessageToMe Canonical Property</span></span>

  
  
<span data-ttu-id="c25b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c25b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c25b1-105">如果专门将此邮件用户命名为"收件人 (，) 收件人，并且此邮件用户不是通讯组列表的一部分，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c25b1-105">Contains TRUE if this messaging user is specifically named as a primary (To) recipient of this message and is not part of a distribution list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c25b1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c25b1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c25b1-107">PR_MESSAGE_TO_ME</span><span class="sxs-lookup"><span data-stu-id="c25b1-107">PR_MESSAGE_TO_ME</span></span>  <br/> |
|<span data-ttu-id="c25b1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c25b1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c25b1-109">0x0057</span><span class="sxs-lookup"><span data-stu-id="c25b1-109">0x0057</span></span>  <br/> |
|<span data-ttu-id="c25b1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c25b1-110">Data type:</span></span>  <br/> |<span data-ttu-id="c25b1-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c25b1-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c25b1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c25b1-112">Area:</span></span>  <br/> |<span data-ttu-id="c25b1-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="c25b1-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c25b1-114">备注</span><span class="sxs-lookup"><span data-stu-id="c25b1-114">Remarks</span></span>

<span data-ttu-id="c25b1-115">此属性提供了一种方便地确定用户名是否显式显示在主收件人列表中，而无需检查列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="c25b1-115">This property provides a convenient way to determine whether the user name appears explicitly in the primary recipient list, without examining all entries in the list.</span></span> 
  
<span data-ttu-id="c25b1-116">此属性还有助于在收到邮件时自动处理收到的邮件。</span><span class="sxs-lookup"><span data-stu-id="c25b1-116">This property also assists automated handling of received messages at the time of receipt.</span></span> <span data-ttu-id="c25b1-117">在传输提供程序的选项中，如果邮件传递用户未直接在收件人表中列出，则此属性包含 FALSE 或不包含此属性。</span><span class="sxs-lookup"><span data-stu-id="c25b1-117">At the transport provider's option, this property either contains FALSE or is not included if the messaging user is not listed directly in the recipient table.</span></span> 
  
<span data-ttu-id="c25b1-118">通讯组列表扩展或盲副本指定导致的邮件传递不会导致设置此属性。</span><span class="sxs-lookup"><span data-stu-id="c25b1-118">Message delivery resulting from distribution list expansion or a blind carbon copy designation does not cause this property to be set.</span></span> <span data-ttu-id="c25b1-119">收件人必须明确命名。</span><span class="sxs-lookup"><span data-stu-id="c25b1-119">The recipient must be explicitly named.</span></span> 
  
<span data-ttu-id="c25b1-120">未发送的邮件通常不会设置 **PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md)) 、PR_MESSAGE_RECIP_ME ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)) 或此属性。 </span><span class="sxs-lookup"><span data-stu-id="c25b1-120">Unsent messages generally do not set the **PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md)), **PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)), or this property.</span></span> <span data-ttu-id="c25b1-121">如果用户在邮件中显示用户可以访问公共邮件存储、其他用户专用存储、磁盘上的文件或其他接收的邮件内嵌入的邮件，则通常包含传输提供程序上次传递邮件时设置的值。</span><span class="sxs-lookup"><span data-stu-id="c25b1-121">If they are present in messages the user can access in public message stores, in other users' private stores, in files on disk, or embedded inside other received messages, they generally contain the values to which they were set the last time a transport provider delivered the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c25b1-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="c25b1-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c25b1-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="c25b1-123">Protocol specifications</span></span>

<span data-ttu-id="c25b1-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c25b1-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c25b1-125">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="c25b1-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c25b1-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c25b1-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c25b1-127">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c25b1-127">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c25b1-128">头文件</span><span class="sxs-lookup"><span data-stu-id="c25b1-128">Header files</span></span>

<span data-ttu-id="c25b1-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c25b1-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="c25b1-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c25b1-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="c25b1-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c25b1-131">Mapitags.h</span></span>
  
> <span data-ttu-id="c25b1-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c25b1-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c25b1-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c25b1-133">See also</span></span>



[<span data-ttu-id="c25b1-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c25b1-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c25b1-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c25b1-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c25b1-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c25b1-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c25b1-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c25b1-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

