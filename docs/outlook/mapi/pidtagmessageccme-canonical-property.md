---
title: PidTagMessageCcMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCcMe
api_type:
- HeaderDef
ms.assetid: 7310a0f2-a109-40a4-99bf-e963d754a067
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7605739dd6d0f0205a1a4f09eb8c45d235c0c179
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329734"
---
# <a name="pidtagmessageccme-canonical-property"></a><span data-ttu-id="81ec1-103">PidTagMessageCcMe 规范属性</span><span class="sxs-lookup"><span data-stu-id="81ec1-103">PidTagMessageCcMe Canonical Property</span></span>

  
  
<span data-ttu-id="81ec1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81ec1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81ec1-105">如果此邮件用户专门指定为此邮件的抄送 (CC) 收件人且不是通讯组列表的一部分, 则该参数为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="81ec1-105">Contains TRUE if this messaging user is specifically named as a carbon copy (CC) recipient of this message and is not part of a distribution list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="81ec1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="81ec1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="81ec1-107">PR_MESSAGE_CC_ME</span><span class="sxs-lookup"><span data-stu-id="81ec1-107">PR_MESSAGE_CC_ME</span></span>  <br/> |
|<span data-ttu-id="81ec1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="81ec1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="81ec1-109">0x0058</span><span class="sxs-lookup"><span data-stu-id="81ec1-109">0x0058</span></span>  <br/> |
|<span data-ttu-id="81ec1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="81ec1-110">Data type:</span></span>  <br/> |<span data-ttu-id="81ec1-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="81ec1-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="81ec1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="81ec1-112">Area:</span></span>  <br/> |<span data-ttu-id="81ec1-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="81ec1-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="81ec1-114">注解</span><span class="sxs-lookup"><span data-stu-id="81ec1-114">Remarks</span></span>

<span data-ttu-id="81ec1-115">此属性提供了一种方便的方法来确定用户名是否显式显示在 "抄送" 收件人列表中, 而不检查列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="81ec1-115">This property provides a convenient way to determine whether the user name appears explicitly in the carbon copy recipient list, without examining all entries in the list.</span></span> 
  
<span data-ttu-id="81ec1-116">此属性还有助于在接收时自动处理收到的邮件。</span><span class="sxs-lookup"><span data-stu-id="81ec1-116">This property also assists automated handling of received messages at the time of receipt.</span></span> <span data-ttu-id="81ec1-117">在传输提供程序的选项中, 如果邮件用户未直接列在收件人表中, 则此属性包含 FALSE 或不设置。</span><span class="sxs-lookup"><span data-stu-id="81ec1-117">At the transport provider's option, this property either contains FALSE or is not set if the messaging user is not listed directly in the recipient table.</span></span> 
  
<span data-ttu-id="81ec1-118">由于通讯组列表展开或密件抄送指定导致的邮件传递不会导致设置此属性。</span><span class="sxs-lookup"><span data-stu-id="81ec1-118">Message delivery resulting from distribution list expansion or a blind carbon copy designation does not cause this property to be set.</span></span> <span data-ttu-id="81ec1-119">收件人必须显式命名。</span><span class="sxs-lookup"><span data-stu-id="81ec1-119">The recipient must be explicitly named.</span></span> 
  
<span data-ttu-id="81ec1-120">未发送的邮件通常不设置此属性、 **PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)) 或**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="81ec1-120">Unsent messages generally do not set this property, **PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)), or **PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)).</span></span> <span data-ttu-id="81ec1-121">如果用户可以访问公用邮件存储区中的其他用户的私人存储、磁盘上的文件或嵌入到其他已接收邮件中的邮件, 则通常会包含它们在上次传输提供程序中所设置的值。传递了邮件。</span><span class="sxs-lookup"><span data-stu-id="81ec1-121">If they are present in messages the user can access in public message stores, in other users' private stores, in files on disk, or embedded inside other received messages, they generally contain the values to which they were set the last time a transport provider delivered the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="81ec1-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="81ec1-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="81ec1-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="81ec1-123">Protocol specifications</span></span>

<span data-ttu-id="81ec1-124">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81ec1-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81ec1-125">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="81ec1-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="81ec1-126">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81ec1-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81ec1-127">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="81ec1-127">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="81ec1-128">头文件</span><span class="sxs-lookup"><span data-stu-id="81ec1-128">Header files</span></span>

<span data-ttu-id="81ec1-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="81ec1-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="81ec1-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="81ec1-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="81ec1-131">Mapitags</span><span class="sxs-lookup"><span data-stu-id="81ec1-131">Mapitags.h</span></span>
  
> <span data-ttu-id="81ec1-132">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="81ec1-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="81ec1-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81ec1-133">See also</span></span>



[<span data-ttu-id="81ec1-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="81ec1-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="81ec1-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="81ec1-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="81ec1-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="81ec1-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="81ec1-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="81ec1-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

