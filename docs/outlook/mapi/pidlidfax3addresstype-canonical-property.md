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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bbe2d6c5fc6683de06602c61aa8ef7b8ca8ada55
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385422"
---
# <a name="pidlidfax3addresstype-canonical-property"></a><span data-ttu-id="7d05b-103">PidLidFax3AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="7d05b-103">PidLidFax3AddressType Canonical Property</span></span>

  
  
<span data-ttu-id="7d05b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7d05b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7d05b-105">指定该联系人的传真地址的地址类型。</span><span class="sxs-lookup"><span data-stu-id="7d05b-105">Specifies the address type for the other contact's fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7d05b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7d05b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7d05b-107">dispidFax3AddrType</span><span class="sxs-lookup"><span data-stu-id="7d05b-107">dispidFax3AddrType</span></span>  <br/> |
|<span data-ttu-id="7d05b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7d05b-108">Property set:</span></span>  <br/> |<span data-ttu-id="7d05b-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="7d05b-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="7d05b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7d05b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7d05b-111">0x000080D2</span><span class="sxs-lookup"><span data-stu-id="7d05b-111">0x000080D2</span></span>  <br/> |
|<span data-ttu-id="7d05b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7d05b-112">Data type:</span></span>  <br/> |<span data-ttu-id="7d05b-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7d05b-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7d05b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7d05b-114">Area:</span></span>  <br/> |<span data-ttu-id="7d05b-115">联系人</span><span class="sxs-lookup"><span data-stu-id="7d05b-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7d05b-116">说明</span><span class="sxs-lookup"><span data-stu-id="7d05b-116">Remarks</span></span>

<span data-ttu-id="7d05b-117">此属性，如果存在此参数，必须设置为"传真"。</span><span class="sxs-lookup"><span data-stu-id="7d05b-117">This property, if present, must be set to "FAX".</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7d05b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7d05b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7d05b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7d05b-119">Protocol specifications</span></span>

<span data-ttu-id="7d05b-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d05b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7d05b-121">提供属性集定义定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7d05b-121">Provides property set definition definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7d05b-122">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7d05b-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7d05b-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7d05b-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7d05b-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7d05b-124">Header files</span></span>

<span data-ttu-id="7d05b-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7d05b-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7d05b-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7d05b-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7d05b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d05b-127">See also</span></span>



[<span data-ttu-id="7d05b-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7d05b-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7d05b-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7d05b-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7d05b-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7d05b-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7d05b-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7d05b-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

