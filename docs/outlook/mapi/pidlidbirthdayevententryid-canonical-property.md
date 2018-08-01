---
title: PidLidBirthdayEventEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBirthdayEventEntryId
api_type:
- COM
ms.assetid: 6807dcfc-d9bd-48a1-a093-3097b2cb107c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4a8cf9ac24f275d8b9cdbe03b5a90477771a2ab4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776700"
---
# <a name="pidlidbirthdayevententryid-canonical-property"></a><span data-ttu-id="19e2c-103">PidLidBirthdayEventEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="19e2c-103">PidLidBirthdayEventEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="19e2c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19e2c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="19e2c-105">指定的值，该值代表联系人的生日可选约会的**EntryId** 。</span><span class="sxs-lookup"><span data-stu-id="19e2c-105">Specifies the **EntryId** of an optional appointment that represents the contact's birthday.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="19e2c-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="19e2c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="19e2c-107">dispidBirthdayEventEID</span><span class="sxs-lookup"><span data-stu-id="19e2c-107">dispidBirthdayEventEID</span></span>  <br/> |
|<span data-ttu-id="19e2c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="19e2c-108">Property set:</span></span>  <br/> |<span data-ttu-id="19e2c-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="19e2c-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="19e2c-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="19e2c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="19e2c-111">0x0000804D</span><span class="sxs-lookup"><span data-stu-id="19e2c-111">0x0000804D</span></span>  <br/> |
|<span data-ttu-id="19e2c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="19e2c-112">Data type:</span></span>  <br/> |<span data-ttu-id="19e2c-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="19e2c-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="19e2c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="19e2c-114">Area:</span></span>  <br/> |<span data-ttu-id="19e2c-115">联系人</span><span class="sxs-lookup"><span data-stu-id="19e2c-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="19e2c-116">备注</span><span class="sxs-lookup"><span data-stu-id="19e2c-116">Remarks</span></span>

<span data-ttu-id="19e2c-117">这通过此属性指定的约会必须使用**dispidApptStateFlags** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md))、 **dispidContactLinkSearchKey** ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)) 和**链接到此联系人dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) 属性，作为中指定[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="19e2c-117">The appointment this is specified by this property must be linked to this contact by using the **dispidApptStateFlags** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)), **dispidContactLinkSearchKey** ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)), and **dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) properties, as specified in [[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="19e2c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="19e2c-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="19e2c-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="19e2c-119">Protocol specifications</span></span>

<span data-ttu-id="19e2c-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="19e2c-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="19e2c-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="19e2c-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="19e2c-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="19e2c-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="19e2c-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="19e2c-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="19e2c-124">头文件</span><span class="sxs-lookup"><span data-stu-id="19e2c-124">Header files</span></span>

<span data-ttu-id="19e2c-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="19e2c-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="19e2c-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="19e2c-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19e2c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19e2c-127">See also</span></span>



[<span data-ttu-id="19e2c-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="19e2c-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="19e2c-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="19e2c-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="19e2c-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="19e2c-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="19e2c-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="19e2c-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
