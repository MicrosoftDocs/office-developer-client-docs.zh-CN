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
# <a name="pidliddistributionlistchecksum-canonical-property"></a><span data-ttu-id="f2e24-103">PidLidDistributionListChecksum 规范属性</span><span class="sxs-lookup"><span data-stu-id="f2e24-103">PidLidDistributionListChecksum Canonical Property</span></span>

  
  
<span data-ttu-id="f2e24-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2e24-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2e24-105">指定个人通讯组列表的 CRC-32 (CRC-32) 多项式校验和。</span><span class="sxs-lookup"><span data-stu-id="f2e24-105">Specifies the 32-bit cyclic redundancy check (CRC-32) polynomial checksum for a personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f2e24-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f2e24-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f2e24-107">dispidDLChecksum</span><span class="sxs-lookup"><span data-stu-id="f2e24-107">dispidDLChecksum</span></span>  <br/> |
|<span data-ttu-id="f2e24-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="f2e24-108">Property set:</span></span>  <br/> |<span data-ttu-id="f2e24-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="f2e24-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="f2e24-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="f2e24-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f2e24-111">0x0000804C</span><span class="sxs-lookup"><span data-stu-id="f2e24-111">0x0000804C</span></span>  <br/> |
|<span data-ttu-id="f2e24-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f2e24-112">Data type:</span></span>  <br/> |<span data-ttu-id="f2e24-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f2e24-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f2e24-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f2e24-114">Area:</span></span>  <br/> |<span data-ttu-id="f2e24-115">联系人</span><span class="sxs-lookup"><span data-stu-id="f2e24-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f2e24-116">备注</span><span class="sxs-lookup"><span data-stu-id="f2e24-116">Remarks</span></span>

<span data-ttu-id="f2e24-117">此属性的值可用于检测何时更新 **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) 属性，而无需更新其他个人通讯组列表成员属性，方法为计算 **dispidDLMembers** 的现有值上的 CRC-32，并比较它和 **dispidDLChecksum** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f2e24-117">The value of this property can be used to detect when the **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) property was updated without updating the other personal distribution list member properties by computing the CRC-32 on the existing value of **dispidDLMembers** and comparing it with the value of the **dispidDLChecksum** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f2e24-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f2e24-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f2e24-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f2e24-119">Protocol specifications</span></span>

<span data-ttu-id="f2e24-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f2e24-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f2e24-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="f2e24-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f2e24-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f2e24-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f2e24-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f2e24-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f2e24-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f2e24-124">Header files</span></span>

<span data-ttu-id="f2e24-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f2e24-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f2e24-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f2e24-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f2e24-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2e24-127">See also</span></span>



[<span data-ttu-id="f2e24-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f2e24-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f2e24-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f2e24-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f2e24-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f2e24-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f2e24-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f2e24-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

