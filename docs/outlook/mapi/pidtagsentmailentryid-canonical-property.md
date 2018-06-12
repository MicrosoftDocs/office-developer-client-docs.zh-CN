---
title: PidTagSentMailEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSentMailEntryId
api_type:
- COM
ms.assetid: 8f14dc15-d7d7-4894-b6a8-0d589f576c42
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 869f7f0bb4ea5e7222201083cb6d41754d241396
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778389"
---
# <a name="pidtagsentmailentryid-canonical-property"></a><span data-ttu-id="dc3ac-103">PidTagSentMailEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc3ac-103">PidTagSentMailEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="dc3ac-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dc3ac-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dc3ac-105">包含邮件应移动后提交的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-105">Contains the entry identifier of the folder where the message should be moved after submission.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc3ac-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="dc3ac-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dc3ac-107">PR_SENTMAIL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="dc3ac-107">PR_SENTMAIL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="dc3ac-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="dc3ac-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dc3ac-109">0x0E0A</span><span class="sxs-lookup"><span data-stu-id="dc3ac-109">0x0E0A</span></span>  <br/> |
|<span data-ttu-id="dc3ac-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dc3ac-110">Data type:</span></span>  <br/> |<span data-ttu-id="dc3ac-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="dc3ac-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="dc3ac-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dc3ac-112">Area:</span></span>  <br/> |<span data-ttu-id="dc3ac-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="dc3ac-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc3ac-114">备注</span><span class="sxs-lookup"><span data-stu-id="dc3ac-114">Remarks</span></span>

<span data-ttu-id="dc3ac-115">此属性通常复制**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 属性，该客户端应用程序的标准发送项目文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-115">This property is often copied from the **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) property, the client application's standard Sent Items folder.</span></span>
  
<span data-ttu-id="dc3ac-116">客户端应用程序使用此属性与**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性控制提交后，一条消息，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-116">The client application uses this property with the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property to control what happens to a message after it is submitted.</span></span> <span data-ttu-id="dc3ac-117">设置，但不是能同时，应为一个或多。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-117">Either one or the other should be set, but not both.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dc3ac-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="dc3ac-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dc3ac-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="dc3ac-119">Protocol specifications</span></span>

<span data-ttu-id="dc3ac-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc3ac-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc3ac-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dc3ac-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc3ac-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc3ac-123">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="dc3ac-124">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc3ac-124">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc3ac-125">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-125">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dc3ac-126">头文件</span><span class="sxs-lookup"><span data-stu-id="dc3ac-126">Header files</span></span>

<span data-ttu-id="dc3ac-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dc3ac-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="dc3ac-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="dc3ac-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dc3ac-129">Mapitags.h</span></span>
  
> <span data-ttu-id="dc3ac-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dc3ac-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc3ac-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc3ac-131">See also</span></span>



[<span data-ttu-id="dc3ac-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dc3ac-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dc3ac-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc3ac-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dc3ac-134">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dc3ac-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dc3ac-135">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dc3ac-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

