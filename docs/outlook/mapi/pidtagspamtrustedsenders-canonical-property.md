---
title: PidTagSpamTrustedSenders 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8e3f0094-e64b-4828-ba8f-5eed35f85366
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 50230a742b093e59e335466d9ab03aa9022e2e61
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388726"
---
# <a name="pidtagspamtrustedsenders-canonical-property"></a><span data-ttu-id="7e9c2-103">PidTagSpamTrustedSenders 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e9c2-103">PidTagSpamTrustedSenders Canonical Property</span></span>

  
  
<span data-ttu-id="7e9c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e9c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e9c2-105">包含以分号分隔的电子邮件地址和组成的受信任的发件人的域列表。</span><span class="sxs-lookup"><span data-stu-id="7e9c2-105">Contains a semicolon-delimited list of email addresses and domains that are made up of trusted senders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7e9c2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7e9c2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7e9c2-107">PR_SPAM_TRUSTED_SENDERS_W</span><span class="sxs-lookup"><span data-stu-id="7e9c2-107">PR_SPAM_TRUSTED_SENDERS_W</span></span>  <br/> |
|<span data-ttu-id="7e9c2-108">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7e9c2-108">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7e9c2-109">0x0418</span><span class="sxs-lookup"><span data-stu-id="7e9c2-109">0x0418</span></span>  <br/> |
|<span data-ttu-id="7e9c2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7e9c2-110">Data type:</span></span>  <br/> |<span data-ttu-id="7e9c2-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7e9c2-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7e9c2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7e9c2-112">Area:</span></span>  <br/> |<span data-ttu-id="7e9c2-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7e9c2-113">Spam</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="7e9c2-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="7e9c2-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7e9c2-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="7e9c2-115">Protocol specifications</span></span>

<span data-ttu-id="7e9c2-116">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e9c2-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e9c2-117">提供属性集定义和相关的 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7e9c2-117">Provides property set definitions and references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7e9c2-118">[[MS OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e9c2-118">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e9c2-119">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="7e9c2-119">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7e9c2-120">头文件</span><span class="sxs-lookup"><span data-stu-id="7e9c2-120">Header files</span></span>

<span data-ttu-id="7e9c2-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7e9c2-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="7e9c2-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7e9c2-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="7e9c2-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7e9c2-123">Mapitags.h</span></span>
  
> <span data-ttu-id="7e9c2-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7e9c2-124">Contains definitions of properties that are listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7e9c2-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e9c2-125">See also</span></span>



[<span data-ttu-id="7e9c2-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7e9c2-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7e9c2-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e9c2-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7e9c2-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7e9c2-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7e9c2-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7e9c2-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

