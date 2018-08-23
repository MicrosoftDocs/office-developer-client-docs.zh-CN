---
title: PidLidFax1OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax1OriginalEntryId
api_type:
- COM
ms.assetid: 0e02dfcd-918e-4d0c-b701-505dee1b32d4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e914cf639caeb64087b80b7d8c3ba61c95b6a1f4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587108"
---
# <a name="pidlidfax1originalentryid-canonical-property"></a><span data-ttu-id="857a3-103">PidLidFax1OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="857a3-103">PidLidFax1OriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="857a3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="857a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="857a3-105">指定联系人的业务传真地址的原始 EntryID。</span><span class="sxs-lookup"><span data-stu-id="857a3-105">Specifies the original EntryID of the contact's business fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="857a3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="857a3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="857a3-107">dispidFax1OriginalEntryID</span><span class="sxs-lookup"><span data-stu-id="857a3-107">dispidFax1OriginalEntryID</span></span>  <br/> |
|<span data-ttu-id="857a3-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="857a3-108">Property set:</span></span>  <br/> |<span data-ttu-id="857a3-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="857a3-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="857a3-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="857a3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="857a3-111">0x000080B5</span><span class="sxs-lookup"><span data-stu-id="857a3-111">0x000080B5</span></span>  <br/> |
|<span data-ttu-id="857a3-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="857a3-112">Data type:</span></span>  <br/> |<span data-ttu-id="857a3-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="857a3-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="857a3-114">区域：</span><span class="sxs-lookup"><span data-stu-id="857a3-114">Area:</span></span>  <br/> |<span data-ttu-id="857a3-115">联系人</span><span class="sxs-lookup"><span data-stu-id="857a3-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="857a3-116">注解</span><span class="sxs-lookup"><span data-stu-id="857a3-116">Remarks</span></span>

<span data-ttu-id="857a3-117">如果存在此参数，此属性，必须指定此传真地址对应的一次性 EntryId。</span><span class="sxs-lookup"><span data-stu-id="857a3-117">This property, if present, must specify the one-off EntryId that corresponds to this fax address.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="857a3-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="857a3-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="857a3-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="857a3-119">Protocol specifications</span></span>

<span data-ttu-id="857a3-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="857a3-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="857a3-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="857a3-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="857a3-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="857a3-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="857a3-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="857a3-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="857a3-124">头文件</span><span class="sxs-lookup"><span data-stu-id="857a3-124">Header files</span></span>

<span data-ttu-id="857a3-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="857a3-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="857a3-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="857a3-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="857a3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="857a3-127">See also</span></span>



[<span data-ttu-id="857a3-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="857a3-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="857a3-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="857a3-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="857a3-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="857a3-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="857a3-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="857a3-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

