---
title: PidLidEmail3OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalEntryId
api_type:
- COM
ms.assetid: b290d4a4-8d70-4656-9254-191c5179662f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dc850be73432873b88d5f6106dd62b0e8fd6e662
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776771"
---
# <a name="pidlidemail3originalentryid-canonical-property"></a><span data-ttu-id="d17f6-103">PidLidEmail3OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d17f6-103">PidLidEmail3OriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="d17f6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d17f6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d17f6-105">指定对象对应于第三个电子邮件地址的**EntryId** 。</span><span class="sxs-lookup"><span data-stu-id="d17f6-105">Specifies the **EntryId** of the object that corresponds to the third email address.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d17f6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d17f6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d17f6-107">dispidEmail3OriginalEntryID</span><span class="sxs-lookup"><span data-stu-id="d17f6-107">dispidEmail3OriginalEntryID</span></span>  <br/> |
|<span data-ttu-id="d17f6-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="d17f6-108">Property set:</span></span>  <br/> |<span data-ttu-id="d17f6-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="d17f6-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="d17f6-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="d17f6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d17f6-111">0x000080A5</span><span class="sxs-lookup"><span data-stu-id="d17f6-111">0x000080A5</span></span>  <br/> |
|<span data-ttu-id="d17f6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d17f6-112">Data type:</span></span>  <br/> |<span data-ttu-id="d17f6-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d17f6-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d17f6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d17f6-114">Area:</span></span>  <br/> |<span data-ttu-id="d17f6-115">联系人</span><span class="sxs-lookup"><span data-stu-id="d17f6-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d17f6-116">说明</span><span class="sxs-lookup"><span data-stu-id="d17f6-116">Remarks</span></span>

<span data-ttu-id="d17f6-117">此属性的值必须是此电子通讯一次性**EntryId**或有效的通讯簿对象**EntryId**。</span><span class="sxs-lookup"><span data-stu-id="d17f6-117">The value of this property must be either a one-off **EntryId** for this electronic address or a valid Address Book object **EntryId**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d17f6-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="d17f6-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d17f6-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="d17f6-119">Protocol specifications</span></span>

<span data-ttu-id="d17f6-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d17f6-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d17f6-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d17f6-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d17f6-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d17f6-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d17f6-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d17f6-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d17f6-124">头文件</span><span class="sxs-lookup"><span data-stu-id="d17f6-124">Header files</span></span>

<span data-ttu-id="d17f6-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d17f6-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="d17f6-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d17f6-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d17f6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d17f6-127">See also</span></span>



[<span data-ttu-id="d17f6-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d17f6-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d17f6-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d17f6-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d17f6-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d17f6-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d17f6-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d17f6-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

