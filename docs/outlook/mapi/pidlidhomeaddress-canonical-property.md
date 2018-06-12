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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 00f40a443d6ab730c8b612fd0fdfd93a1fd5cf52
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776878"
---
# <a name="pidlidhomeaddress-canonical-property"></a><span data-ttu-id="7ceb6-103">PidLidHomeAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ceb6-103">PidLidHomeAddress Canonical Property</span></span>

  
  
<span data-ttu-id="7ceb6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7ceb6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7ceb6-105">指定联系人的住宅地址的完整地址。</span><span class="sxs-lookup"><span data-stu-id="7ceb6-105">Specifies the complete address of the contact's home address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7ceb6-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="7ceb6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7ceb6-107">dispidHomeAddress</span><span class="sxs-lookup"><span data-stu-id="7ceb6-107">dispidHomeAddress</span></span>  <br/> |
|<span data-ttu-id="7ceb6-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7ceb6-108">Property set:</span></span>  <br/> |<span data-ttu-id="7ceb6-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="7ceb6-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="7ceb6-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7ceb6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7ceb6-111">0x0000801A</span><span class="sxs-lookup"><span data-stu-id="7ceb6-111">0x0000801A</span></span>  <br/> |
|<span data-ttu-id="7ceb6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7ceb6-112">Data type:</span></span>  <br/> |<span data-ttu-id="7ceb6-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7ceb6-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7ceb6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7ceb6-114">Area:</span></span>  <br/> |<span data-ttu-id="7ceb6-115">联系人</span><span class="sxs-lookup"><span data-stu-id="7ceb6-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7ceb6-116">备注</span><span class="sxs-lookup"><span data-stu-id="7ceb6-116">Remarks</span></span>

<span data-ttu-id="7ceb6-117">此属性应为其他物理地址属性的组合，并基于客户端区域设置。</span><span class="sxs-lookup"><span data-stu-id="7ceb6-117">This property should be a combination of other physical address properties, and is based on client locale.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7ceb6-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7ceb6-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7ceb6-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7ceb6-119">Protocol specifications</span></span>

<span data-ttu-id="7ceb6-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7ceb6-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7ceb6-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7ceb6-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7ceb6-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7ceb6-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7ceb6-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7ceb6-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7ceb6-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7ceb6-124">Header files</span></span>

<span data-ttu-id="7ceb6-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7ceb6-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7ceb6-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7ceb6-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7ceb6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ceb6-127">See also</span></span>



[<span data-ttu-id="7ceb6-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7ceb6-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7ceb6-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7ceb6-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7ceb6-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7ceb6-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7ceb6-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7ceb6-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

