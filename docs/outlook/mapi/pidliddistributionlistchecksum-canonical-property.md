---
title: PidLidDistributionListChecksum 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidLidDistributionListChecksum
api_type:
- COM
ms.assetid: bd50ab34-caae-4258-8afc-769e3cbc5220
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bba1e78d79800b1c8e56ad50ce1abb144d4c9aae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776742"
---
# <a name="pidliddistributionlistchecksum-canonical-property"></a><span data-ttu-id="b4dfd-103">PidLidDistributionListChecksum 规范属性</span><span class="sxs-lookup"><span data-stu-id="b4dfd-103">PidLidDistributionListChecksum Canonical Property</span></span>

  
  
<span data-ttu-id="b4dfd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b4dfd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b4dfd-105">指定的 32 位循环冗余复选 (CRC-32) 多项式校验和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b4dfd-105">Specifies the 32-bit cyclic redundancy check (CRC-32) polynomial checksum for a personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b4dfd-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b4dfd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b4dfd-107">dispidDLChecksum</span><span class="sxs-lookup"><span data-stu-id="b4dfd-107">dispidDLChecksum</span></span>  <br/> |
|<span data-ttu-id="b4dfd-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b4dfd-108">Property set:</span></span>  <br/> |<span data-ttu-id="b4dfd-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="b4dfd-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="b4dfd-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b4dfd-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b4dfd-111">0x0000804C</span><span class="sxs-lookup"><span data-stu-id="b4dfd-111">0x0000804C</span></span>  <br/> |
|<span data-ttu-id="b4dfd-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b4dfd-112">Data type:</span></span>  <br/> |<span data-ttu-id="b4dfd-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b4dfd-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b4dfd-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b4dfd-114">Area:</span></span>  <br/> |<span data-ttu-id="b4dfd-115">联系人</span><span class="sxs-lookup"><span data-stu-id="b4dfd-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b4dfd-116">备注</span><span class="sxs-lookup"><span data-stu-id="b4dfd-116">Remarks</span></span>

<span data-ttu-id="b4dfd-117">此属性的值可用于检测何时**dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) 属性已更新而不是通过计算 CRC-32 上现有更新其他个人通讯组列表成员属性**dispidDLMembers** 、 将其与**dispidDLChecksum**属性的值进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="b4dfd-117">The value of this property can be used to detect when the **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) property was updated without updating the other personal distribution list member properties by computing the CRC-32 on the existing value of **dispidDLMembers** and comparing it with the value of the **dispidDLChecksum** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b4dfd-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b4dfd-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b4dfd-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b4dfd-119">Protocol specifications</span></span>

<span data-ttu-id="b4dfd-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4dfd-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b4dfd-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b4dfd-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b4dfd-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b4dfd-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b4dfd-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b4dfd-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b4dfd-124">头文件</span><span class="sxs-lookup"><span data-stu-id="b4dfd-124">Header files</span></span>

<span data-ttu-id="b4dfd-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b4dfd-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="b4dfd-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b4dfd-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b4dfd-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4dfd-127">See also</span></span>



[<span data-ttu-id="b4dfd-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b4dfd-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b4dfd-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b4dfd-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b4dfd-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b4dfd-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b4dfd-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b4dfd-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
