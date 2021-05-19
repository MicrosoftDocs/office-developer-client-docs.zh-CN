---
title: PidTagOriginalSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSearchKey
api_type:
- COM
ms.assetid: ac5eb91d-31c9-459b-bb22-f4ccfc92d1db
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d106a216e8d72c126f3293f9d492db73992c3872
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355291"
---
# <a name="pidtagoriginalsearchkey-canonical-property"></a><span data-ttu-id="93aa1-103">PidTagOriginalSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="93aa1-103">PidTagOriginalSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="93aa1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="93aa1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="93aa1-105">包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始搜索键。</span><span class="sxs-lookup"><span data-stu-id="93aa1-105">Contains the original search key for an entry copied from an address book to a personal address book or other writeable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="93aa1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="93aa1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="93aa1-107">PR_ORIGINAL_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="93aa1-107">PR_ORIGINAL_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="93aa1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="93aa1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="93aa1-109">0x3A14</span><span class="sxs-lookup"><span data-stu-id="93aa1-109">0x3A14</span></span>  <br/> |
|<span data-ttu-id="93aa1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="93aa1-110">Data type:</span></span>  <br/> |<span data-ttu-id="93aa1-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="93aa1-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="93aa1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="93aa1-112">Area:</span></span>  <br/> |<span data-ttu-id="93aa1-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="93aa1-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="93aa1-114">备注</span><span class="sxs-lookup"><span data-stu-id="93aa1-114">Remarks</span></span>

<span data-ttu-id="93aa1-115">此属性是包含有关所复制条目的原始源的信息的属性之一。</span><span class="sxs-lookup"><span data-stu-id="93aa1-115">This property is one of the properties that contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="93aa1-116">对于未读报告，此属性包含生成报告的原始邮件收件人的搜索密钥副本。</span><span class="sxs-lookup"><span data-stu-id="93aa1-116">For a nonread report, this property contains a copy of the search key of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="93aa1-117">如果原始收件人是通讯组列表的一部分，则为报告保留通讯组列表的搜索键。</span><span class="sxs-lookup"><span data-stu-id="93aa1-117">When the original recipient is part of a distribution list, the search key of the distribution list is preserved for the report.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="93aa1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="93aa1-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="93aa1-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="93aa1-119">Protocol specifications</span></span>

<span data-ttu-id="93aa1-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="93aa1-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="93aa1-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="93aa1-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="93aa1-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="93aa1-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="93aa1-123">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="93aa1-123">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="93aa1-124">头文件</span><span class="sxs-lookup"><span data-stu-id="93aa1-124">Header files</span></span>

<span data-ttu-id="93aa1-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="93aa1-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="93aa1-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="93aa1-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="93aa1-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="93aa1-127">Mapitags.h</span></span>
  
> <span data-ttu-id="93aa1-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="93aa1-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="93aa1-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93aa1-129">See also</span></span>



[<span data-ttu-id="93aa1-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="93aa1-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="93aa1-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="93aa1-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="93aa1-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="93aa1-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="93aa1-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="93aa1-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

