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
ms.openlocfilehash: b20234d079fb38fac878efe92390defcba6e5d1f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335572"
---
# <a name="pidlidanniversaryevententryid-canonical-property"></a><span data-ttu-id="4d446-103">PidLidAnniversaryEventEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d446-103">PidLidAnniversaryEventEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="4d446-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d446-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d446-105">指定表示联系人周年纪念的约会的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="4d446-105">Specifies the entry identifier of the appointment that represents the contact's anniversary.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d446-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4d446-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4d446-107">dispidAnniversaryEventEID</span><span class="sxs-lookup"><span data-stu-id="4d446-107">dispidAnniversaryEventEID</span></span>  <br/> |
|<span data-ttu-id="4d446-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="4d446-108">Property set:</span></span>  <br/> |<span data-ttu-id="4d446-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="4d446-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="4d446-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="4d446-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="4d446-111">0x0000804E</span><span class="sxs-lookup"><span data-stu-id="4d446-111">0x0000804E</span></span>  <br/> |
|<span data-ttu-id="4d446-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4d446-112">Data type:</span></span>  <br/> |<span data-ttu-id="4d446-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4d446-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4d446-114">区域：</span><span class="sxs-lookup"><span data-stu-id="4d446-114">Area:</span></span>  <br/> |<span data-ttu-id="4d446-115">Contact</span><span class="sxs-lookup"><span data-stu-id="4d446-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d446-116">注解</span><span class="sxs-lookup"><span data-stu-id="4d446-116">Remarks</span></span>

<span data-ttu-id="4d446-117">**dispidAnniversaryEventEID**属性指定的约会必须使用**dispidContactLinkEntry** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md))、 **dispidContactLinkSearchKey** ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)) 和**dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) 属性, 如[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="4d446-117">The appointment specified by the **dispidAnniversaryEventEID** property must be linked to this contact by using the **dispidContactLinkEntry** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)), **dispidContactLinkSearchKey** ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)), and **dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) properties, as detailed in [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4d446-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4d446-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4d446-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4d446-119">Protocol specifications</span></span>

<span data-ttu-id="4d446-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d446-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d446-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4d446-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4d446-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4d446-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4d446-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4d446-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4d446-124">头文件</span><span class="sxs-lookup"><span data-stu-id="4d446-124">Header files</span></span>

<span data-ttu-id="4d446-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4d446-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="4d446-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4d446-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4d446-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d446-127">See also</span></span>



[<span data-ttu-id="4d446-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4d446-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4d446-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d446-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4d446-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4d446-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4d446-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4d446-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

