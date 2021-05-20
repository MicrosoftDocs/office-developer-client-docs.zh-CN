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
ms.openlocfilehash: c659b77767fddc4c783732082c2eb65c68af8dbf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431664"
---
# <a name="pidtagrecipientcertificate-canonical-property"></a><span data-ttu-id="52f61-103">PidTagRecipientCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="52f61-103">PidTagRecipientCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="52f61-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52f61-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52f61-105">包含邮件收件人的 ASN.1 证书，用于报告。</span><span class="sxs-lookup"><span data-stu-id="52f61-105">Contains a message recipient's ASN.1 certificate for use in a report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="52f61-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="52f61-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="52f61-107">PR_RECIPIENT_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="52f61-107">PR_RECIPIENT_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="52f61-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="52f61-108">Identifier:</span></span>  <br/> |<span data-ttu-id="52f61-109">0x0C13</span><span class="sxs-lookup"><span data-stu-id="52f61-109">0x0C13</span></span>  <br/> |
|<span data-ttu-id="52f61-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="52f61-110">Data type:</span></span>  <br/> |<span data-ttu-id="52f61-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="52f61-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="52f61-112">区域：</span><span class="sxs-lookup"><span data-stu-id="52f61-112">Area:</span></span>  <br/> |<span data-ttu-id="52f61-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="52f61-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="52f61-114">备注</span><span class="sxs-lookup"><span data-stu-id="52f61-114">Remarks</span></span>

<span data-ttu-id="52f61-115">此属性是[PidTagUserCertificate PR_USER_CERTIFICATE (PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) 的副本，以用于报表。 </span><span class="sxs-lookup"><span data-stu-id="52f61-115">This property is a copy of the recipient's **PR_USER_CERTIFICATE** ([PidTagUserCertificate](pidtagusercertificate-canonical-property.md)) property for use in a report.</span></span> <span data-ttu-id="52f61-116">它可用于向发起人证明收件人实际上收到了邮件，送达报告不一定指示这一点。</span><span class="sxs-lookup"><span data-stu-id="52f61-116">It can be used to prove to the originator that the recipient actually received the message, which a delivery report does not necessarily indicate.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="52f61-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="52f61-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="52f61-118">头文件</span><span class="sxs-lookup"><span data-stu-id="52f61-118">Header files</span></span>

<span data-ttu-id="52f61-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="52f61-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="52f61-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="52f61-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="52f61-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="52f61-121">Mapitags.h</span></span>
  
> <span data-ttu-id="52f61-122">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="52f61-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="52f61-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52f61-123">See also</span></span>



[<span data-ttu-id="52f61-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="52f61-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="52f61-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="52f61-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="52f61-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="52f61-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="52f61-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="52f61-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

