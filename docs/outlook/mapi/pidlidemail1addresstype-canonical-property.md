---
title: PidLidEmail1AddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail1AddressType
api_type:
- COM
ms.assetid: 9a0bc2b5-d0c9-405b-97ad-b43839f908da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5ec99eba9759588ff69fc141de8e499ee87d69ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586324"
---
# <a name="pidlidemail1addresstype-canonical-property"></a><span data-ttu-id="33c40-103">PidLidEmail1AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="33c40-103">PidLidEmail1AddressType Canonical Property</span></span>

  
  
<span data-ttu-id="33c40-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33c40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33c40-105">指定的第一个电子邮件地址的地址类型。</span><span class="sxs-lookup"><span data-stu-id="33c40-105">Specifies the address type of the first email address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="33c40-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="33c40-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="33c40-107">dispidEmail1AddrType</span><span class="sxs-lookup"><span data-stu-id="33c40-107">dispidEmail1AddrType</span></span>  <br/> |
|<span data-ttu-id="33c40-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="33c40-108">Property set:</span></span>  <br/> |<span data-ttu-id="33c40-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="33c40-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="33c40-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="33c40-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="33c40-111">0x00008082</span><span class="sxs-lookup"><span data-stu-id="33c40-111">0x00008082</span></span>  <br/> |
|<span data-ttu-id="33c40-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="33c40-112">Data type:</span></span>  <br/> |<span data-ttu-id="33c40-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="33c40-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="33c40-114">区域：</span><span class="sxs-lookup"><span data-stu-id="33c40-114">Area:</span></span>  <br/> |<span data-ttu-id="33c40-115">联系人</span><span class="sxs-lookup"><span data-stu-id="33c40-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33c40-116">注解</span><span class="sxs-lookup"><span data-stu-id="33c40-116">Remarks</span></span>

<span data-ttu-id="33c40-117">如果存在此参数，此属性值必须是有效的地址类型。</span><span class="sxs-lookup"><span data-stu-id="33c40-117">If present, this property value must be a valid address type.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="33c40-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="33c40-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="33c40-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="33c40-119">Protocol specifications</span></span>

<span data-ttu-id="33c40-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33c40-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33c40-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="33c40-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="33c40-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33c40-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33c40-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="33c40-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="33c40-124">头文件</span><span class="sxs-lookup"><span data-stu-id="33c40-124">Header files</span></span>

<span data-ttu-id="33c40-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="33c40-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="33c40-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="33c40-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="33c40-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33c40-127">See also</span></span>



[<span data-ttu-id="33c40-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="33c40-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="33c40-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="33c40-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="33c40-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="33c40-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="33c40-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="33c40-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

