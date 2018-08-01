---
title: PidLidAnniversaryEventEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAnniversaryEventEntryId
api_type:
- COM
ms.assetid: 177b2b87-7a06-4d53-8f03-5bec5632c2dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 78096affce8fa03cc3efc8f0ca0c7048c2f9aae9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776593"
---
# <a name="pidlidanniversaryevententryid-canonical-property"></a><span data-ttu-id="eed50-103">PidLidAnniversaryEventEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="eed50-103">PidLidAnniversaryEventEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="eed50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="eed50-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="eed50-105">指定约会值，该值代表该联系人的周年日的项标识符。</span><span class="sxs-lookup"><span data-stu-id="eed50-105">Specifies the entry identifier of the appointment that represents the contact's anniversary.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eed50-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="eed50-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="eed50-107">dispidAnniversaryEventEID</span><span class="sxs-lookup"><span data-stu-id="eed50-107">dispidAnniversaryEventEID</span></span>  <br/> |
|<span data-ttu-id="eed50-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="eed50-108">Property set:</span></span>  <br/> |<span data-ttu-id="eed50-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="eed50-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="eed50-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="eed50-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="eed50-111">0x0000804E</span><span class="sxs-lookup"><span data-stu-id="eed50-111">0x0000804E</span></span>  <br/> |
|<span data-ttu-id="eed50-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="eed50-112">Data type:</span></span>  <br/> |<span data-ttu-id="eed50-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="eed50-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="eed50-114">区域：</span><span class="sxs-lookup"><span data-stu-id="eed50-114">Area:</span></span>  <br/> |<span data-ttu-id="eed50-115">联系人</span><span class="sxs-lookup"><span data-stu-id="eed50-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="eed50-116">说明</span><span class="sxs-lookup"><span data-stu-id="eed50-116">Remarks</span></span>

<span data-ttu-id="eed50-117">约会**dispidAnniversaryEventEID**属性指定必须使用**dispidContactLinkEntry** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md))， **dispidContactLinkSearchKey** ([链接到此联系人PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md))，而将**dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) 属性，作为详细中[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="eed50-117">The appointment specified by the **dispidAnniversaryEventEID** property must be linked to this contact by using the **dispidContactLinkEntry** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)), **dispidContactLinkSearchKey** ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)), and **dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) properties, as detailed in [[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="eed50-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="eed50-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="eed50-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="eed50-119">Protocol specifications</span></span>

<span data-ttu-id="eed50-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eed50-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eed50-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="eed50-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="eed50-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="eed50-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="eed50-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="eed50-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="eed50-124">头文件</span><span class="sxs-lookup"><span data-stu-id="eed50-124">Header files</span></span>

<span data-ttu-id="eed50-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="eed50-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="eed50-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="eed50-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eed50-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eed50-127">See also</span></span>



[<span data-ttu-id="eed50-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="eed50-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="eed50-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="eed50-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="eed50-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="eed50-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="eed50-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="eed50-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

