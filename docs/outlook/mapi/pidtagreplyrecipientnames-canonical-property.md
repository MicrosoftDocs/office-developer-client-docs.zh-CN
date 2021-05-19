---
title: PidTagReplyRecipientNames 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientNames
api_type:
- COM
ms.assetid: f5ae6124-3e44-400f-95c2-24b19f3085b5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 02dcbcccd003fb0b53356da11a3b90b38e632c2a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355172"
---
# <a name="pidtagreplyrecipientnames-canonical-property"></a><span data-ttu-id="49020-103">PidTagReplyRecipientNames 规范属性</span><span class="sxs-lookup"><span data-stu-id="49020-103">PidTagReplyRecipientNames Canonical Property</span></span>

  
  
<span data-ttu-id="49020-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="49020-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="49020-105">包含要获取答复的收件人的显示名称列表。</span><span class="sxs-lookup"><span data-stu-id="49020-105">Contains a list of display names for recipients that are to get a reply.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="49020-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="49020-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="49020-107">PR_REPLY_RECIPIENT_NAMES、PR_REPLY_RECIPIENT_NAMES_A、PR_REPLY_RECIPIENT_NAMES_W</span><span class="sxs-lookup"><span data-stu-id="49020-107">PR_REPLY_RECIPIENT_NAMES, PR_REPLY_RECIPIENT_NAMES_A, PR_REPLY_RECIPIENT_NAMES_W</span></span>  <br/> |
|<span data-ttu-id="49020-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="49020-108">Identifier:</span></span>  <br/> |<span data-ttu-id="49020-109">0x0050</span><span class="sxs-lookup"><span data-stu-id="49020-109">0x0050</span></span>  <br/> |
|<span data-ttu-id="49020-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="49020-110">Data type:</span></span>  <br/> |<span data-ttu-id="49020-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="49020-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="49020-112">区域：</span><span class="sxs-lookup"><span data-stu-id="49020-112">Area:</span></span>  <br/> |<span data-ttu-id="49020-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="49020-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="49020-114">备注</span><span class="sxs-lookup"><span data-stu-id="49020-114">Remarks</span></span>

<span data-ttu-id="49020-115">这些属性包含用分号分隔的显示名称。</span><span class="sxs-lookup"><span data-stu-id="49020-115">These properties contain the display names separated by semicolons.</span></span>
  
<span data-ttu-id="49020-116">当此属性不存在时，答复将仅发送给[PidTagSenderName](pidtagsendername-canonical-property.md) PR_SENDER_NAME (标识) 用户。 </span><span class="sxs-lookup"><span data-stu-id="49020-116">When this property is not present, a reply is sent only to the user identified by the **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) property.</span></span> <span data-ttu-id="49020-117">如果 **PR_REPLY_RECIPIENT_ENTRIES (** [PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 并且定义了这些属性，则答复将发送给这两个属性标识的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="49020-117">When **PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) and these properties are defined, the reply is sent to all of the recipients identified by these two properties.</span></span> <span data-ttu-id="49020-118">传输提供程序使用这些属性覆盖常见的回复逻辑。</span><span class="sxs-lookup"><span data-stu-id="49020-118">A transport provider uses these properties to override the usual reply logic.</span></span>
  
<span data-ttu-id="49020-119">如果PR_REPLY_RECIPIENT_ENTRIES **属性** 或这些属性，则还必须设置另一个属性。</span><span class="sxs-lookup"><span data-stu-id="49020-119">If either **PR_REPLY_RECIPIENT_ENTRIES** or these properties are set, the other property must be set also.</span></span> <span data-ttu-id="49020-120">这些属性必须包含相同数量的收件人，并且必须按相同的顺序包含它们。</span><span class="sxs-lookup"><span data-stu-id="49020-120">These properties must contain the same number of recipients, and they must contain them in the same order.</span></span> <span data-ttu-id="49020-121">如果未能遵守这些要求，可能会导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="49020-121">Failure to observe these requirements can cause unpredictable results.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="49020-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="49020-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="49020-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="49020-123">Protocol specifications</span></span>

<span data-ttu-id="49020-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="49020-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="49020-125">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="49020-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="49020-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="49020-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="49020-127">指定允许对电子邮件执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="49020-127">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="49020-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="49020-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="49020-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="49020-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="49020-130">头文件</span><span class="sxs-lookup"><span data-stu-id="49020-130">Header files</span></span>

<span data-ttu-id="49020-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="49020-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="49020-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="49020-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="49020-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="49020-133">Mapitags.h</span></span>
  
> <span data-ttu-id="49020-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="49020-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="49020-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49020-135">See also</span></span>



[<span data-ttu-id="49020-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="49020-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="49020-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="49020-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="49020-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="49020-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="49020-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="49020-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

