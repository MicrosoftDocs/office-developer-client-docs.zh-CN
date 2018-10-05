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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396391"
---
# <a name="pidtagtemplateid-canonical-property"></a><span data-ttu-id="07947-103">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="07947-103">PidTagTemplateid Canonical Property</span></span>

  
  
<span data-ttu-id="07947-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07947-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07947-105">包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))，表示为永久条目 ID 格式。</span><span class="sxs-lookup"><span data-stu-id="07947-105">Contains the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), expressed as a permanent entry ID format.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="07947-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="07947-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="07947-107">PR_TEMPLATEID</span><span class="sxs-lookup"><span data-stu-id="07947-107">PR_TEMPLATEID</span></span>  <br/> |
|<span data-ttu-id="07947-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="07947-108">Identifier:</span></span>  <br/> |<span data-ttu-id="07947-109">0x3902</span><span class="sxs-lookup"><span data-stu-id="07947-109">0x3902</span></span>  <br/> |
|<span data-ttu-id="07947-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="07947-110">Data type:</span></span>  <br/> |<span data-ttu-id="07947-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="07947-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="07947-112">区域：</span><span class="sxs-lookup"><span data-stu-id="07947-112">Area:</span></span>  <br/> |<span data-ttu-id="07947-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="07947-113">MAPI Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="07947-114">说明</span><span class="sxs-lookup"><span data-stu-id="07947-114">Remarks</span></span>

<span data-ttu-id="07947-115">此值必须存在以名称服务提供程序界面 (NSPI) 服务器上的所有通讯簿对象，它可分辨的名称 (DN) 必须与值匹配的**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))，并且其 DN 必须按照 DN 格式指定特定于对象的类型。</span><span class="sxs-lookup"><span data-stu-id="07947-115">This value must be present for all address book objects on an Name Service Provider Interface (NSPI) server, its distinguished name (DN) must match the value for **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), and its DN must follow the DN format specification particular to the type of object.</span></span> 
  
<span data-ttu-id="07947-116">该属性不存在于对象上的脱机通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="07947-116">This property is not present on objects in an offline address book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="07947-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="07947-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="07947-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="07947-118">Protocol specifications</span></span>

<span data-ttu-id="07947-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="07947-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="07947-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="07947-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="07947-121">[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="07947-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="07947-122">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="07947-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="07947-123">头文件</span><span class="sxs-lookup"><span data-stu-id="07947-123">Header files</span></span>

<span data-ttu-id="07947-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="07947-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="07947-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="07947-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="07947-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="07947-126">Mapitags.h</span></span>
  
> <span data-ttu-id="07947-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="07947-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="07947-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07947-128">See also</span></span>



[<span data-ttu-id="07947-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="07947-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="07947-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="07947-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="07947-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="07947-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="07947-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="07947-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

