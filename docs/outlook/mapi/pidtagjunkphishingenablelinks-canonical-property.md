---
title: PidTagJunkPhishingEnableLinks 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkPhishingEnableLinks
api_type:
- HeaderDef
ms.assetid: 6b885c36-6e27-4f74-95c3-ce1cdc8a808a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7caeaa84602c9eb9a4384e9520edd866d72adbb1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397742"
---
# <a name="pidtagjunkphishingenablelinks-canonical-property"></a><span data-ttu-id="a39cb-103">PidTagJunkPhishingEnableLinks 规范属性</span><span class="sxs-lookup"><span data-stu-id="a39cb-103">PidTagJunkPhishingEnableLinks Canonical Property</span></span>

  
  
<span data-ttu-id="a39cb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a39cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a39cb-105">表示，如果为 true，则应忽略邮件上的网络钓鱼戳。</span><span class="sxs-lookup"><span data-stu-id="a39cb-105">Signifies, if TRUE, that the phishing stamp on the message should be ignored.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a39cb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a39cb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a39cb-107">PR_JUNK_PHISHING_ENABLE_LINKS</span><span class="sxs-lookup"><span data-stu-id="a39cb-107">PR_JUNK_PHISHING_ENABLE_LINKS</span></span>  <br/> |
|<span data-ttu-id="a39cb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a39cb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a39cb-109">0x6107</span><span class="sxs-lookup"><span data-stu-id="a39cb-109">0x6107</span></span>  <br/> |
|<span data-ttu-id="a39cb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a39cb-110">Data type:</span></span>  <br/> |<span data-ttu-id="a39cb-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="a39cb-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="a39cb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a39cb-112">Area:</span></span>  <br/> |<span data-ttu-id="a39cb-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a39cb-113">Spam</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="a39cb-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="a39cb-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a39cb-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="a39cb-115">Protocol specifications</span></span>

<span data-ttu-id="a39cb-116">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a39cb-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a39cb-117">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a39cb-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a39cb-118">[[MS OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a39cb-118">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a39cb-119">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a39cb-119">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="a39cb-120">[[MS OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a39cb-120">[[MS-OXPHISH]](https://msdn.microsoft.com/library/ed49ab26-ba13-4d4c-8a94-98d4ceecd4b7%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a39cb-121">标识，并将标记旨在到非可靠来源欺骗透露敏感信息 （如密码和其他个人信息） 的收件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a39cb-121">Identifies and marks email messages that are designed to trick recipients into divulging sensitive information (such as passwords and other personal information) to a non-trustworthy source.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a39cb-122">头文件</span><span class="sxs-lookup"><span data-stu-id="a39cb-122">Header files</span></span>

<span data-ttu-id="a39cb-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a39cb-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="a39cb-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a39cb-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="a39cb-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a39cb-125">Mapitags.h</span></span>
  
> <span data-ttu-id="a39cb-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a39cb-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a39cb-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a39cb-127">See also</span></span>



[<span data-ttu-id="a39cb-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a39cb-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a39cb-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a39cb-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a39cb-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a39cb-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a39cb-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a39cb-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

