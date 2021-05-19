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
# <a name="pidtagtemplateid-canonical-property"></a><span data-ttu-id="5ed73-103">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ed73-103">PidTagTemplateid Canonical Property</span></span>

  
  
<span data-ttu-id="5ed73-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5ed73-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5ed73-105">包含 PR_ENTRYID **(** [PidTagEntryId](pidtagentryid-canonical-property.md)) ，表示为永久条目 ID 格式。</span><span class="sxs-lookup"><span data-stu-id="5ed73-105">Contains the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), expressed as a permanent entry ID format.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ed73-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5ed73-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5ed73-107">PR_TEMPLATEID</span><span class="sxs-lookup"><span data-stu-id="5ed73-107">PR_TEMPLATEID</span></span>  <br/> |
|<span data-ttu-id="5ed73-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5ed73-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5ed73-109">0x3902</span><span class="sxs-lookup"><span data-stu-id="5ed73-109">0x3902</span></span>  <br/> |
|<span data-ttu-id="5ed73-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5ed73-110">Data type:</span></span>  <br/> |<span data-ttu-id="5ed73-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5ed73-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5ed73-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5ed73-112">Area:</span></span>  <br/> |<span data-ttu-id="5ed73-113">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="5ed73-113">MAPI Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5ed73-114">备注</span><span class="sxs-lookup"><span data-stu-id="5ed73-114">Remarks</span></span>

<span data-ttu-id="5ed73-115">对于名称服务提供程序接口 (NSPI) 服务器上的所有通讯簿对象，此值必须存在，其可分辨名称 (DN) 必须与 PR_EMAIL_ADDRESS ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md) **)** 的值匹配，并且其 DN 必须遵循 DN 格式规范（特别是对象类型）。</span><span class="sxs-lookup"><span data-stu-id="5ed73-115">This value must be present for all address book objects on an Name Service Provider Interface (NSPI) server, its distinguished name (DN) must match the value for **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)), and its DN must follow the DN format specification particular to the type of object.</span></span> 
  
<span data-ttu-id="5ed73-116">脱机通讯簿中的对象上不存在此属性。</span><span class="sxs-lookup"><span data-stu-id="5ed73-116">This property is not present on objects in an offline address book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5ed73-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5ed73-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5ed73-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="5ed73-118">Protocol specifications</span></span>

<span data-ttu-id="5ed73-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ed73-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ed73-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="5ed73-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5ed73-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ed73-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ed73-122">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5ed73-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5ed73-123">头文件</span><span class="sxs-lookup"><span data-stu-id="5ed73-123">Header files</span></span>

<span data-ttu-id="5ed73-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5ed73-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="5ed73-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5ed73-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="5ed73-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5ed73-126">Mapitags.h</span></span>
  
> <span data-ttu-id="5ed73-127">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5ed73-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5ed73-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed73-128">See also</span></span>



[<span data-ttu-id="5ed73-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5ed73-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5ed73-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ed73-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5ed73-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5ed73-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5ed73-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5ed73-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

