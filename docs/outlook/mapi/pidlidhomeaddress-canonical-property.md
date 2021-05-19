---
title: PidLidHomeAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidHomeAddress
api_type:
- COM
ms.assetid: 5e9c4258-46de-476e-8a64-be9e35a23a8b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8facbb2d3b4e83afc5fb4944607956c289f0bccb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357741"
---
# <a name="pidlidhomeaddress-canonical-property"></a><span data-ttu-id="e0a7d-103">PidLidHomeAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0a7d-103">PidLidHomeAddress Canonical Property</span></span>

  
  
<span data-ttu-id="e0a7d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0a7d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0a7d-105">指定联系人住宅地址的完整地址。</span><span class="sxs-lookup"><span data-stu-id="e0a7d-105">Specifies the complete address of the contact's home address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e0a7d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e0a7d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e0a7d-107">dispidHomeAddress</span><span class="sxs-lookup"><span data-stu-id="e0a7d-107">dispidHomeAddress</span></span>  <br/> |
|<span data-ttu-id="e0a7d-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="e0a7d-108">Property set:</span></span>  <br/> |<span data-ttu-id="e0a7d-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="e0a7d-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="e0a7d-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="e0a7d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e0a7d-111">0x0000801A</span><span class="sxs-lookup"><span data-stu-id="e0a7d-111">0x0000801A</span></span>  <br/> |
|<span data-ttu-id="e0a7d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e0a7d-112">Data type:</span></span>  <br/> |<span data-ttu-id="e0a7d-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e0a7d-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e0a7d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e0a7d-114">Area:</span></span>  <br/> |<span data-ttu-id="e0a7d-115">联系人</span><span class="sxs-lookup"><span data-stu-id="e0a7d-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e0a7d-116">备注</span><span class="sxs-lookup"><span data-stu-id="e0a7d-116">Remarks</span></span>

<span data-ttu-id="e0a7d-117">此属性应该是其他物理地址属性的组合，并且基于客户端区域设置。</span><span class="sxs-lookup"><span data-stu-id="e0a7d-117">This property should be a combination of other physical address properties, and is based on client locale.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e0a7d-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="e0a7d-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e0a7d-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="e0a7d-119">Protocol specifications</span></span>

<span data-ttu-id="e0a7d-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0a7d-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0a7d-121">提供属性集定义和对相关协议Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="e0a7d-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e0a7d-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e0a7d-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e0a7d-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e0a7d-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e0a7d-124">头文件</span><span class="sxs-lookup"><span data-stu-id="e0a7d-124">Header files</span></span>

<span data-ttu-id="e0a7d-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0a7d-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="e0a7d-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e0a7d-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e0a7d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0a7d-127">See also</span></span>



[<span data-ttu-id="e0a7d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e0a7d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e0a7d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e0a7d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e0a7d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e0a7d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e0a7d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e0a7d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

