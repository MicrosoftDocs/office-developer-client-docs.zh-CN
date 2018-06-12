---
title: PidLidFax3AddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax3AddressType
api_type:
- COM
ms.assetid: 77e22ecc-a4fa-4bd2-b0dd-bd58183b7485
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 531784100ce19372a26a12e9338bf76c386dbb5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776817"
---
# <a name="pidlidfax3addresstype-canonical-property"></a><span data-ttu-id="7200f-103">PidLidFax3AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="7200f-103">PidLidFax3AddressType Canonical Property</span></span>

  
  
<span data-ttu-id="7200f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7200f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7200f-105">指定该联系人的传真地址的地址类型。</span><span class="sxs-lookup"><span data-stu-id="7200f-105">Specifies the address type for the other contact's fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7200f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="7200f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7200f-107">dispidFax3AddrType</span><span class="sxs-lookup"><span data-stu-id="7200f-107">dispidFax3AddrType</span></span>  <br/> |
|<span data-ttu-id="7200f-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7200f-108">Property set:</span></span>  <br/> |<span data-ttu-id="7200f-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="7200f-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="7200f-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7200f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7200f-111">0x000080D2</span><span class="sxs-lookup"><span data-stu-id="7200f-111">0x000080D2</span></span>  <br/> |
|<span data-ttu-id="7200f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7200f-112">Data type:</span></span>  <br/> |<span data-ttu-id="7200f-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7200f-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7200f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7200f-114">Area:</span></span>  <br/> |<span data-ttu-id="7200f-115">联系人</span><span class="sxs-lookup"><span data-stu-id="7200f-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7200f-116">备注</span><span class="sxs-lookup"><span data-stu-id="7200f-116">Remarks</span></span>

<span data-ttu-id="7200f-117">此属性，如果存在此参数，必须设置为"传真"。</span><span class="sxs-lookup"><span data-stu-id="7200f-117">This property, if present, must be set to "FAX".</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7200f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7200f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7200f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7200f-119">Protocol specifications</span></span>

<span data-ttu-id="7200f-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7200f-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7200f-121">提供属性集定义定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7200f-121">Provides property set definition definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7200f-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7200f-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7200f-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7200f-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7200f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7200f-124">Header files</span></span>

<span data-ttu-id="7200f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7200f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7200f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7200f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7200f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7200f-127">See also</span></span>



[<span data-ttu-id="7200f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7200f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7200f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7200f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7200f-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7200f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7200f-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7200f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

