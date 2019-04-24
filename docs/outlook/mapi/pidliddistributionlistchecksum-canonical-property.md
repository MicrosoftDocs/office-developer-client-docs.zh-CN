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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ac1f0d839b1ea059ec2b8d94556808bea3850862
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357608"
---
# <a name="pidliddistributionlistchecksum-canonical-property"></a><span data-ttu-id="10f52-103">PidLidDistributionListChecksum 规范属性</span><span class="sxs-lookup"><span data-stu-id="10f52-103">PidLidDistributionListChecksum Canonical Property</span></span>

  
  
<span data-ttu-id="10f52-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="10f52-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="10f52-105">指定个人通讯组列表的32位循环冗余检查 (CRC-32) 多项式校验和。</span><span class="sxs-lookup"><span data-stu-id="10f52-105">Specifies the 32-bit cyclic redundancy check (CRC-32) polynomial checksum for a personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="10f52-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="10f52-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="10f52-107">dispidDLChecksum</span><span class="sxs-lookup"><span data-stu-id="10f52-107">dispidDLChecksum</span></span>  <br/> |
|<span data-ttu-id="10f52-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="10f52-108">Property set:</span></span>  <br/> |<span data-ttu-id="10f52-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="10f52-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="10f52-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="10f52-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="10f52-111">0x0000804C</span><span class="sxs-lookup"><span data-stu-id="10f52-111">0x0000804C</span></span>  <br/> |
|<span data-ttu-id="10f52-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="10f52-112">Data type:</span></span>  <br/> |<span data-ttu-id="10f52-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="10f52-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="10f52-114">区域：</span><span class="sxs-lookup"><span data-stu-id="10f52-114">Area:</span></span>  <br/> |<span data-ttu-id="10f52-115">Contact</span><span class="sxs-lookup"><span data-stu-id="10f52-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="10f52-116">注解</span><span class="sxs-lookup"><span data-stu-id="10f52-116">Remarks</span></span>

<span data-ttu-id="10f52-117">此属性的值可用于检测**dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) 属性何时更新, 而不更新其他个人通讯组列表成员属性, 方法是在现有计算机上计算 CRC-32**dispidDLMembers**的值, 并将其与**dispidDLChecksum**属性的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="10f52-117">The value of this property can be used to detect when the **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) property was updated without updating the other personal distribution list member properties by computing the CRC-32 on the existing value of **dispidDLMembers** and comparing it with the value of the **dispidDLChecksum** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="10f52-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="10f52-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="10f52-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="10f52-119">Protocol specifications</span></span>

<span data-ttu-id="10f52-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="10f52-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="10f52-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="10f52-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="10f52-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="10f52-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="10f52-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="10f52-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="10f52-124">头文件</span><span class="sxs-lookup"><span data-stu-id="10f52-124">Header files</span></span>

<span data-ttu-id="10f52-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="10f52-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="10f52-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="10f52-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="10f52-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10f52-127">See also</span></span>



[<span data-ttu-id="10f52-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="10f52-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="10f52-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="10f52-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="10f52-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="10f52-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="10f52-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="10f52-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

