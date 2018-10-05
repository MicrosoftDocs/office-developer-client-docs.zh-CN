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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7aef8e9ba605d47b110a496e46f629df60a28ea
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398806"
---
# <a name="pidtagsentmailentryid-canonical-property"></a><span data-ttu-id="5e070-103">PidTagSentMailEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="5e070-103">PidTagSentMailEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="5e070-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e070-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5e070-105">包含邮件应移动后提交的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="5e070-105">Contains the entry identifier of the folder where the message should be moved after submission.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5e070-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5e070-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5e070-107">PR_SENTMAIL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5e070-107">PR_SENTMAIL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="5e070-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5e070-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5e070-109">0x0E0A</span><span class="sxs-lookup"><span data-stu-id="5e070-109">0x0E0A</span></span>  <br/> |
|<span data-ttu-id="5e070-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5e070-110">Data type:</span></span>  <br/> |<span data-ttu-id="5e070-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5e070-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5e070-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5e070-112">Area:</span></span>  <br/> |<span data-ttu-id="5e070-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="5e070-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5e070-114">说明</span><span class="sxs-lookup"><span data-stu-id="5e070-114">Remarks</span></span>

<span data-ttu-id="5e070-115">此属性通常复制**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 属性，该客户端应用程序的标准发送项目文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5e070-115">This property is often copied from the **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) property, the client application's standard Sent Items folder.</span></span>
  
<span data-ttu-id="5e070-116">客户端应用程序使用此属性与**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性控制提交后，一条消息，会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="5e070-116">The client application uses this property with the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property to control what happens to a message after it is submitted.</span></span> <span data-ttu-id="5e070-117">设置，但不是能同时，应为一个或多。</span><span class="sxs-lookup"><span data-stu-id="5e070-117">Either one or the other should be set, but not both.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5e070-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="5e070-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5e070-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="5e070-119">Protocol specifications</span></span>

<span data-ttu-id="5e070-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5e070-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5e070-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5e070-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5e070-122">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5e070-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5e070-123">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="5e070-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="5e070-124">[[MS OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5e070-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5e070-125">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="5e070-125">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5e070-126">头文件</span><span class="sxs-lookup"><span data-stu-id="5e070-126">Header files</span></span>

<span data-ttu-id="5e070-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5e070-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="5e070-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5e070-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="5e070-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5e070-129">Mapitags.h</span></span>
  
> <span data-ttu-id="5e070-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5e070-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5e070-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e070-131">See also</span></span>



[<span data-ttu-id="5e070-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5e070-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5e070-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5e070-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5e070-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5e070-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5e070-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5e070-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

