---
title: PidTagOriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayName
api_type:
- COM
ms.assetid: 176245d9-724d-44f1-b7a3-eddf652533b2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2b7aef416beb9eee70aeff8cf20cb38ae8e7993f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355473"
---
# <a name="pidtagoriginaldisplayname-canonical-property"></a><span data-ttu-id="e979a-103">PidTagOriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="e979a-103">PidTagOriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="e979a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e979a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e979a-105">包含从通讯簿显示名称个人通讯簿或其他可写通讯簿的条目的原始记录。</span><span class="sxs-lookup"><span data-stu-id="e979a-105">Contains the original display name for an entry copied from an address book to a personal address book or other writable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e979a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e979a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e979a-107">PR_ORIGINAL_DISPLAY_NAME、PR_ORIGINAL_DISPLAY_NAME_A、PR_ORIGINAL_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="e979a-107">PR_ORIGINAL_DISPLAY_NAME, PR_ORIGINAL_DISPLAY_NAME_A, PR_ORIGINAL_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="e979a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e979a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e979a-109">0x3A13</span><span class="sxs-lookup"><span data-stu-id="e979a-109">0x3A13</span></span>  <br/> |
|<span data-ttu-id="e979a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e979a-110">Data type:</span></span>  <br/> |<span data-ttu-id="e979a-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e979a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e979a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e979a-112">Area:</span></span>  <br/> |<span data-ttu-id="e979a-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="e979a-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e979a-114">备注</span><span class="sxs-lookup"><span data-stu-id="e979a-114">Remarks</span></span>

<span data-ttu-id="e979a-115">这些属性包含有关所复制条目的原始源的信息。</span><span class="sxs-lookup"><span data-stu-id="e979a-115">These properties contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="e979a-116">对于未读报告，这些属性包含生成显示名称的原始邮件收件人的邮件副本的副本。</span><span class="sxs-lookup"><span data-stu-id="e979a-116">For a nonread report, these properties contain a copy of the display name of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="e979a-117">如果原始收件人是通讯组列表的一部分，则显示名称保留通讯组列表的列表的列表。</span><span class="sxs-lookup"><span data-stu-id="e979a-117">When the original recipient is part of a distribution list, the display name of the distribution list is preserved for the report.</span></span>
  
<span data-ttu-id="e979a-118">客户端应用程序可以使用这些属性，通过提供要比较的未更改显示名称条目的"欺骗"。</span><span class="sxs-lookup"><span data-stu-id="e979a-118">A client application can use these properties to prevent alteration or "spoofing" of entries, by giving an unaltered copy of the display name to compare.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e979a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="e979a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e979a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="e979a-120">Protocol specifications</span></span>

<span data-ttu-id="e979a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e979a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e979a-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e979a-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e979a-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e979a-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e979a-124">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e979a-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e979a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="e979a-125">Header files</span></span>

<span data-ttu-id="e979a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e979a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="e979a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e979a-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="e979a-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e979a-128">Mapitags.h</span></span>
  
> <span data-ttu-id="e979a-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e979a-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e979a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e979a-130">See also</span></span>



[<span data-ttu-id="e979a-131">PidTagTransmittableDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="e979a-131">PidTagTransmittableDisplayName Canonical Property</span></span>](pidtagtransmittabledisplayname-canonical-property.md)


[<span data-ttu-id="e979a-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e979a-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e979a-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e979a-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e979a-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e979a-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e979a-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e979a-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

