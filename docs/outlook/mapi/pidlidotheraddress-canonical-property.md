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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eaf6c8706b6f51a297fda3015b9ce9c5277760bc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585960"
---
# <a name="pidlidotheraddress-canonical-property"></a><span data-ttu-id="ec2b1-103">PidLidOtherAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec2b1-103">PidLidOtherAddress Canonical Property</span></span>

  
  
<span data-ttu-id="ec2b1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec2b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec2b1-105">指定联系人的完整地址的其他地址。</span><span class="sxs-lookup"><span data-stu-id="ec2b1-105">Specifies the complete address of the contact's other address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ec2b1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ec2b1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ec2b1-107">dispidOtherAddress</span><span class="sxs-lookup"><span data-stu-id="ec2b1-107">dispidOtherAddress</span></span>  <br/> |
|<span data-ttu-id="ec2b1-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ec2b1-108">Property set:</span></span>  <br/> |<span data-ttu-id="ec2b1-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="ec2b1-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="ec2b1-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ec2b1-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ec2b1-111">0x0000801C</span><span class="sxs-lookup"><span data-stu-id="ec2b1-111">0x0000801C</span></span>  <br/> |
|<span data-ttu-id="ec2b1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ec2b1-112">Data type:</span></span>  <br/> |<span data-ttu-id="ec2b1-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ec2b1-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ec2b1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ec2b1-114">Area:</span></span>  <br/> |<span data-ttu-id="ec2b1-115">联系人</span><span class="sxs-lookup"><span data-stu-id="ec2b1-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ec2b1-116">注解</span><span class="sxs-lookup"><span data-stu-id="ec2b1-116">Remarks</span></span>

<span data-ttu-id="ec2b1-117">此属性应为其他物理地址属性的组合，并基于客户端区域设置。</span><span class="sxs-lookup"><span data-stu-id="ec2b1-117">This property should be a combination of other physical address properties, and is based on client locale.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ec2b1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="ec2b1-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ec2b1-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="ec2b1-119">Protocol specifications</span></span>

<span data-ttu-id="ec2b1-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec2b1-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec2b1-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ec2b1-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ec2b1-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec2b1-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec2b1-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="ec2b1-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ec2b1-124">头文件</span><span class="sxs-lookup"><span data-stu-id="ec2b1-124">Header files</span></span>

<span data-ttu-id="ec2b1-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ec2b1-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ec2b1-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ec2b1-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ec2b1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec2b1-127">See also</span></span>



[<span data-ttu-id="ec2b1-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ec2b1-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ec2b1-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec2b1-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ec2b1-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ec2b1-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ec2b1-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ec2b1-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

