---
title: PidLidOtherAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOtherAddress
api_type:
- COM
ms.assetid: 2b8acb69-4c84-4075-8457-d7aadce26c73
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b8b490242d6c0260fb4ba4335846da06a0e73d4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776950"
---
# <a name="pidlidotheraddress-canonical-property"></a><span data-ttu-id="87fdc-103">PidLidOtherAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="87fdc-103">PidLidOtherAddress Canonical Property</span></span>

  
  
<span data-ttu-id="87fdc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="87fdc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="87fdc-105">指定联系人的完整地址的其他地址。</span><span class="sxs-lookup"><span data-stu-id="87fdc-105">Specifies the complete address of the contact's other address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="87fdc-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="87fdc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="87fdc-107">dispidOtherAddress</span><span class="sxs-lookup"><span data-stu-id="87fdc-107">dispidOtherAddress</span></span>  <br/> |
|<span data-ttu-id="87fdc-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="87fdc-108">Property set:</span></span>  <br/> |<span data-ttu-id="87fdc-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="87fdc-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="87fdc-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="87fdc-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="87fdc-111">0x0000801C</span><span class="sxs-lookup"><span data-stu-id="87fdc-111">0x0000801C</span></span>  <br/> |
|<span data-ttu-id="87fdc-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="87fdc-112">Data type:</span></span>  <br/> |<span data-ttu-id="87fdc-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="87fdc-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="87fdc-114">区域：</span><span class="sxs-lookup"><span data-stu-id="87fdc-114">Area:</span></span>  <br/> |<span data-ttu-id="87fdc-115">联系人</span><span class="sxs-lookup"><span data-stu-id="87fdc-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="87fdc-116">备注</span><span class="sxs-lookup"><span data-stu-id="87fdc-116">Remarks</span></span>

<span data-ttu-id="87fdc-117">此属性应为其他物理地址属性的组合，并基于客户端区域设置。</span><span class="sxs-lookup"><span data-stu-id="87fdc-117">This property should be a combination of other physical address properties, and is based on client locale.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="87fdc-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="87fdc-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="87fdc-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="87fdc-119">Protocol specifications</span></span>

<span data-ttu-id="87fdc-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87fdc-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87fdc-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="87fdc-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="87fdc-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87fdc-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87fdc-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="87fdc-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="87fdc-124">头文件</span><span class="sxs-lookup"><span data-stu-id="87fdc-124">Header files</span></span>

<span data-ttu-id="87fdc-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="87fdc-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="87fdc-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="87fdc-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87fdc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87fdc-127">See also</span></span>



[<span data-ttu-id="87fdc-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="87fdc-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="87fdc-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="87fdc-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="87fdc-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="87fdc-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="87fdc-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="87fdc-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

