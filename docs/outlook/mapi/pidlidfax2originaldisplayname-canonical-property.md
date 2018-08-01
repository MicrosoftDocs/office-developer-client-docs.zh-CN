---
title: PidLidFax2OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax2OriginalDisplayName
api_type:
- COM
ms.assetid: 7f521e27-834c-4fb5-9782-2c5d1380690f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d009118b8e4c11f70e9545302e2fd7ab9b43f00e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776800"
---
# <a name="pidlidfax2originaldisplayname-canonical-property"></a><span data-ttu-id="84a72-103">PidLidFax2OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="84a72-103">PidLidFax2OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="84a72-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="84a72-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="84a72-105">指定联系人的住宅传真地址的原始显示名称。</span><span class="sxs-lookup"><span data-stu-id="84a72-105">Specifies the original display name of the contact's home fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="84a72-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="84a72-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="84a72-107">dispidFax2OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="84a72-107">dispidFax2OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="84a72-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="84a72-108">Property set:</span></span>  <br/> |<span data-ttu-id="84a72-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="84a72-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="84a72-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="84a72-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="84a72-111">0x000080C4</span><span class="sxs-lookup"><span data-stu-id="84a72-111">0x000080C4</span></span>  <br/> |
|<span data-ttu-id="84a72-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="84a72-112">Data type:</span></span>  <br/> |<span data-ttu-id="84a72-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="84a72-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="84a72-114">区域：</span><span class="sxs-lookup"><span data-stu-id="84a72-114">Area:</span></span>  <br/> |<span data-ttu-id="84a72-115">联系人</span><span class="sxs-lookup"><span data-stu-id="84a72-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="84a72-116">说明</span><span class="sxs-lookup"><span data-stu-id="84a72-116">Remarks</span></span>

<span data-ttu-id="84a72-117">此属性，如果存在此参数，必须将设置为**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="84a72-117">This property, if present, must be set to the same value as the **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="84a72-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="84a72-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="84a72-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="84a72-119">Protocol specifications</span></span>

<span data-ttu-id="84a72-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="84a72-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="84a72-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="84a72-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="84a72-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="84a72-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="84a72-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="84a72-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="84a72-124">头文件</span><span class="sxs-lookup"><span data-stu-id="84a72-124">Header files</span></span>

<span data-ttu-id="84a72-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="84a72-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="84a72-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="84a72-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="84a72-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84a72-127">See also</span></span>



[<span data-ttu-id="84a72-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="84a72-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="84a72-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="84a72-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="84a72-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="84a72-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="84a72-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="84a72-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

