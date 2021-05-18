---
title: PidTagSpamTrustedRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 59f43316-3ff6-4ed0-bc29-b31039192b08
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 521bdb280776be28d3526471888834bbd7da0b9f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359449"
---
# <a name="pidtagspamtrustedrecipients-canonical-property"></a><span data-ttu-id="a2205-103">PidTagSpamTrustedRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="a2205-103">PidTagSpamTrustedRecipients Canonical Property</span></span>
 
<span data-ttu-id="a2205-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2205-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2205-105">包含一个以分号分隔的电子邮件地址和域的列表，这些地址和域代表受信任的收件人。</span><span class="sxs-lookup"><span data-stu-id="a2205-105">Contains a semicolon-delimited list of email addresses and domains that represent the trusted recipients.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a2205-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a2205-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a2205-107">PR_SPAM_TRUSTED_RECIPIENTS_W</span><span class="sxs-lookup"><span data-stu-id="a2205-107">PR_SPAM_TRUSTED_RECIPIENTS_W</span></span>  <br/> |
|<span data-ttu-id="a2205-108">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="a2205-108">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a2205-109">0x0419</span><span class="sxs-lookup"><span data-stu-id="a2205-109">0x0419</span></span>  <br/> |
|<span data-ttu-id="a2205-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a2205-110">Data type:</span></span>  <br/> |<span data-ttu-id="a2205-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a2205-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a2205-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a2205-112">Area:</span></span>  <br/> |<span data-ttu-id="a2205-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a2205-113">Spam</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="a2205-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="a2205-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a2205-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="a2205-115">Protocol specifications</span></span>

<span data-ttu-id="a2205-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2205-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a2205-117">提供属性集定义和对相关协议规范Microsoft Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="a2205-117">Provides property set definitions and references to related Microsoft Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a2205-118">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2205-118">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a2205-119">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="a2205-119">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a2205-120">头文件</span><span class="sxs-lookup"><span data-stu-id="a2205-120">Header files</span></span>

<span data-ttu-id="a2205-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a2205-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="a2205-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a2205-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="a2205-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a2205-123">Mapitags.h</span></span>
  
> <span data-ttu-id="a2205-124">包含列为备用名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a2205-124">Contains definitions of properties that are listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a2205-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2205-125">See also</span></span>

- [<span data-ttu-id="a2205-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a2205-126">MAPI Properties</span></span>](mapi-properties.md) 
- [<span data-ttu-id="a2205-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a2205-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)  
- [<span data-ttu-id="a2205-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a2205-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)  
- [<span data-ttu-id="a2205-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a2205-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

