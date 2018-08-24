---
title: PidTagRecipientCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientCertificate
api_type:
- COM
ms.assetid: 7c5c749e-5463-4935-85b5-32219d06f782
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 464db3d360f6e872ac28f8d7cbec842d8b521f7e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585113"
---
# <a name="pidtagrecipientcertificate-canonical-property"></a><span data-ttu-id="c95f0-103">PidTagRecipientCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="c95f0-103">PidTagRecipientCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="c95f0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c95f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c95f0-105">包含用于报告的邮件收件人的 ASN.1 证书。</span><span class="sxs-lookup"><span data-stu-id="c95f0-105">Contains a message recipient's ASN.1 certificate for use in a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c95f0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c95f0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c95f0-107">PR_RECIPIENT_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="c95f0-107">PR_RECIPIENT_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="c95f0-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c95f0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c95f0-109">0x0C13</span><span class="sxs-lookup"><span data-stu-id="c95f0-109">0x0C13</span></span>  <br/> |
|<span data-ttu-id="c95f0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c95f0-110">Data type:</span></span>  <br/> |<span data-ttu-id="c95f0-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c95f0-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c95f0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c95f0-112">Area:</span></span>  <br/> |<span data-ttu-id="c95f0-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="c95f0-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c95f0-114">注解</span><span class="sxs-lookup"><span data-stu-id="c95f0-114">Remarks</span></span>

<span data-ttu-id="c95f0-115">此属性是收件人的**PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) 属性用于在报表中的副本。</span><span class="sxs-lookup"><span data-stu-id="c95f0-115">This property is a copy of the recipient's **PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) property for use in a report.</span></span> <span data-ttu-id="c95f0-116">它可以用于发起方证明收件人实际接收邮件的送达报告不一定表示。</span><span class="sxs-lookup"><span data-stu-id="c95f0-116">It can be used to prove to the originator that the recipient actually received the message, which a delivery report does not necessarily indicate.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c95f0-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="c95f0-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c95f0-118">头文件</span><span class="sxs-lookup"><span data-stu-id="c95f0-118">Header files</span></span>

<span data-ttu-id="c95f0-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c95f0-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="c95f0-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c95f0-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="c95f0-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c95f0-121">Mapitags.h</span></span>
  
> <span data-ttu-id="c95f0-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c95f0-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c95f0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c95f0-123">See also</span></span>



[<span data-ttu-id="c95f0-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c95f0-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c95f0-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c95f0-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c95f0-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c95f0-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c95f0-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c95f0-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

