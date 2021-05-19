---
title: PidLidFax1OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax1OriginalDisplayName
api_type:
- COM
ms.assetid: 1520e27f-e261-4a94-be06-31cd47bea4a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e24637ed9e29ab887833b6ed5ff7453353684a47
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332128"
---
# <a name="pidlidfax1originaldisplayname-canonical-property"></a><span data-ttu-id="6cba5-103">PidLidFax1OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="6cba5-103">PidLidFax1OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="6cba5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6cba5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6cba5-105">指定联系人显示名称传真地址的原始地址。</span><span class="sxs-lookup"><span data-stu-id="6cba5-105">Specifies the original display name of the contact's business fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6cba5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6cba5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6cba5-107">dispidFax1OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="6cba5-107">dispidFax1OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="6cba5-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="6cba5-108">Property set:</span></span>  <br/> |<span data-ttu-id="6cba5-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="6cba5-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="6cba5-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="6cba5-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6cba5-111">0x000080B4</span><span class="sxs-lookup"><span data-stu-id="6cba5-111">0x000080B4</span></span>  <br/> |
|<span data-ttu-id="6cba5-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6cba5-112">Data type:</span></span>  <br/> |<span data-ttu-id="6cba5-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6cba5-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="6cba5-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6cba5-114">Area:</span></span>  <br/> |<span data-ttu-id="6cba5-115">联系人</span><span class="sxs-lookup"><span data-stu-id="6cba5-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6cba5-116">备注</span><span class="sxs-lookup"><span data-stu-id="6cba5-116">Remarks</span></span>

<span data-ttu-id="6cba5-117">此属性（如果存在）必须设置为与[PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)属性PR_NORMALIZED_SUBJECT (相同) 值。 </span><span class="sxs-lookup"><span data-stu-id="6cba5-117">This property, if present, must be set to the same value as the **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6cba5-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6cba5-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6cba5-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6cba5-119">Protocol specifications</span></span>

<span data-ttu-id="6cba5-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cba5-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6cba5-121">提供属性集定义和对相关协议Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="6cba5-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6cba5-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cba5-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6cba5-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6cba5-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6cba5-124">头文件</span><span class="sxs-lookup"><span data-stu-id="6cba5-124">Header files</span></span>

<span data-ttu-id="6cba5-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6cba5-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="6cba5-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6cba5-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6cba5-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cba5-127">See also</span></span>



[<span data-ttu-id="6cba5-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6cba5-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6cba5-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6cba5-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6cba5-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6cba5-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6cba5-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6cba5-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

