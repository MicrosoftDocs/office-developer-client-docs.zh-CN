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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bb51e9a602bd5c2e59bb56fdbf44fddc39651de6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778155"
---
# <a name="pidtagrecipientcertificate-canonical-property"></a><span data-ttu-id="0c6fe-103">PidTagRecipientCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c6fe-103">PidTagRecipientCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="0c6fe-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0c6fe-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0c6fe-105">包含用于报告的邮件收件人的 ASN.1 证书。</span><span class="sxs-lookup"><span data-stu-id="0c6fe-105">Contains a message recipient's ASN.1 certificate for use in a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0c6fe-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="0c6fe-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0c6fe-107">PR_RECIPIENT_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="0c6fe-107">PR_RECIPIENT_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="0c6fe-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0c6fe-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0c6fe-109">0x0C13</span><span class="sxs-lookup"><span data-stu-id="0c6fe-109">0x0C13</span></span>  <br/> |
|<span data-ttu-id="0c6fe-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0c6fe-110">Data type:</span></span>  <br/> |<span data-ttu-id="0c6fe-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0c6fe-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0c6fe-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0c6fe-112">Area:</span></span>  <br/> |<span data-ttu-id="0c6fe-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="0c6fe-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0c6fe-114">备注</span><span class="sxs-lookup"><span data-stu-id="0c6fe-114">Remarks</span></span>

<span data-ttu-id="0c6fe-115">此属性是收件人的**PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) 属性用于在报表中的副本。</span><span class="sxs-lookup"><span data-stu-id="0c6fe-115">This property is a copy of the recipient's **PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) property for use in a report.</span></span> <span data-ttu-id="0c6fe-116">它可以用于发起方证明收件人实际接收邮件的送达报告不一定表示。</span><span class="sxs-lookup"><span data-stu-id="0c6fe-116">It can be used to prove to the originator that the recipient actually received the message, which a delivery report does not necessarily indicate.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0c6fe-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="0c6fe-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0c6fe-118">头文件</span><span class="sxs-lookup"><span data-stu-id="0c6fe-118">Header files</span></span>

<span data-ttu-id="0c6fe-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0c6fe-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="0c6fe-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0c6fe-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="0c6fe-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0c6fe-121">Mapitags.h</span></span>
  
> <span data-ttu-id="0c6fe-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0c6fe-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c6fe-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c6fe-123">See also</span></span>



[<span data-ttu-id="0c6fe-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0c6fe-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0c6fe-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c6fe-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0c6fe-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0c6fe-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0c6fe-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0c6fe-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

