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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342509"
---
# <a name="pidtagsentmailentryid-canonical-property"></a><span data-ttu-id="156b8-103">PidTagSentMailEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="156b8-103">PidTagSentMailEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="156b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="156b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="156b8-105">包含应在提交后将邮件移动到的文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="156b8-105">Contains the entry identifier of the folder where the message should be moved after submission.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="156b8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="156b8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="156b8-107">PR_SENTMAIL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="156b8-107">PR_SENTMAIL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="156b8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="156b8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="156b8-109">0x0E0A</span><span class="sxs-lookup"><span data-stu-id="156b8-109">0x0E0A</span></span>  <br/> |
|<span data-ttu-id="156b8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="156b8-110">Data type:</span></span>  <br/> |<span data-ttu-id="156b8-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="156b8-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="156b8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="156b8-112">Area:</span></span>  <br/> |<span data-ttu-id="156b8-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="156b8-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="156b8-114">备注</span><span class="sxs-lookup"><span data-stu-id="156b8-114">Remarks</span></span>

<span data-ttu-id="156b8-115">此属性 **PR_IPM_SENTMAIL_ENTRYID** 通常从 [PidTagIpmSentMailEntryId (PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) 属性（客户端应用程序的标准"已发送项目"文件夹）复制。</span><span class="sxs-lookup"><span data-stu-id="156b8-115">This property is often copied from the **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) property, the client application's standard Sent Items folder.</span></span>
  
<span data-ttu-id="156b8-116">客户端应用程序将此属性与 PR_DELETE_AFTER_SUBMIT  ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性一起用来控制邮件提交后会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="156b8-116">The client application uses this property with the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property to control what happens to a message after it is submitted.</span></span> <span data-ttu-id="156b8-117">应设置其中一个，但不能同时设置两者。</span><span class="sxs-lookup"><span data-stu-id="156b8-117">Either one or the other should be set, but not both.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="156b8-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="156b8-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="156b8-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="156b8-119">Protocol specifications</span></span>

<span data-ttu-id="156b8-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="156b8-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="156b8-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="156b8-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="156b8-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="156b8-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="156b8-123">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="156b8-123">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="156b8-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="156b8-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="156b8-125">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="156b8-125">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="156b8-126">头文件</span><span class="sxs-lookup"><span data-stu-id="156b8-126">Header files</span></span>

<span data-ttu-id="156b8-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="156b8-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="156b8-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="156b8-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="156b8-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="156b8-129">Mapitags.h</span></span>
  
> <span data-ttu-id="156b8-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="156b8-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="156b8-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="156b8-131">See also</span></span>



[<span data-ttu-id="156b8-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="156b8-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="156b8-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="156b8-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="156b8-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="156b8-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="156b8-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="156b8-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

