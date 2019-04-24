---
title: PidTagTemplateid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTemplateid
api_type:
- COM
ms.assetid: 1a418c76-ebc7-47f2-ac91-797162e6e099
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96bcd15606771bd112568ad94133507ab14b2bcd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358819"
---
# <a name="pidtagtemplateid-canonical-property"></a><span data-ttu-id="0d84e-103">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d84e-103">PidTagTemplateid Canonical Property</span></span>

  
  
<span data-ttu-id="0d84e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d84e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d84e-105">包含以永久条目 ID 格式表示的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="0d84e-105">Contains the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), expressed as a permanent entry ID format.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d84e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0d84e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0d84e-107">PR_TEMPLATEID</span><span class="sxs-lookup"><span data-stu-id="0d84e-107">PR_TEMPLATEID</span></span>  <br/> |
|<span data-ttu-id="0d84e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0d84e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0d84e-109">0x3902</span><span class="sxs-lookup"><span data-stu-id="0d84e-109">0x3902</span></span>  <br/> |
|<span data-ttu-id="0d84e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0d84e-110">Data type:</span></span>  <br/> |<span data-ttu-id="0d84e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0d84e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0d84e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0d84e-112">Area:</span></span>  <br/> |<span data-ttu-id="0d84e-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="0d84e-113">MAPI Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d84e-114">注解</span><span class="sxs-lookup"><span data-stu-id="0d84e-114">Remarks</span></span>

<span data-ttu-id="0d84e-115">对于名称服务提供程序接口 (NSPI) 服务器上的所有通讯簿对象, 此值必须存在, 其可分辨名称 (DN) 必须与**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 的值相匹配, 并且其 dn 必须遵循 DN 格式特定于对象类型的规范。</span><span class="sxs-lookup"><span data-stu-id="0d84e-115">This value must be present for all address book objects on an Name Service Provider Interface (NSPI) server, its distinguished name (DN) must match the value for **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), and its DN must follow the DN format specification particular to the type of object.</span></span> 
  
<span data-ttu-id="0d84e-116">此属性不存在于脱机通讯簿中的对象上。</span><span class="sxs-lookup"><span data-stu-id="0d84e-116">This property is not present on objects in an offline address book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0d84e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="0d84e-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0d84e-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="0d84e-118">Protocol specifications</span></span>

<span data-ttu-id="0d84e-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d84e-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d84e-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0d84e-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0d84e-121">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d84e-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d84e-122">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0d84e-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0d84e-123">头文件</span><span class="sxs-lookup"><span data-stu-id="0d84e-123">Header files</span></span>

<span data-ttu-id="0d84e-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0d84e-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="0d84e-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0d84e-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="0d84e-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0d84e-126">Mapitags.h</span></span>
  
> <span data-ttu-id="0d84e-127">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0d84e-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0d84e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d84e-128">See also</span></span>



[<span data-ttu-id="0d84e-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0d84e-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0d84e-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d84e-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0d84e-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0d84e-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0d84e-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d84e-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

