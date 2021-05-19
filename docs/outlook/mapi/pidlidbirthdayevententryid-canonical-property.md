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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 90d1dc8a9ce7f94238e8754cfbcaf88b702928f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342019"
---
# <a name="pidlidbirthdayevententryid-canonical-property"></a><span data-ttu-id="21929-103">PidLidBirthdayEventEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="21929-103">PidLidBirthdayEventEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="21929-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21929-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21929-105">指定代表联系人的生日的可选约会的 **EntryId。**</span><span class="sxs-lookup"><span data-stu-id="21929-105">Specifies the **EntryId** of an optional appointment that represents the contact's birthday.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="21929-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="21929-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="21929-107">dispidBirthdayEventEID</span><span class="sxs-lookup"><span data-stu-id="21929-107">dispidBirthdayEventEID</span></span>  <br/> |
|<span data-ttu-id="21929-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="21929-108">Property set:</span></span>  <br/> |<span data-ttu-id="21929-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="21929-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="21929-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="21929-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="21929-111">0x0000804D</span><span class="sxs-lookup"><span data-stu-id="21929-111">0x0000804D</span></span>  <br/> |
|<span data-ttu-id="21929-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="21929-112">Data type:</span></span>  <br/> |<span data-ttu-id="21929-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="21929-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="21929-114">区域：</span><span class="sxs-lookup"><span data-stu-id="21929-114">Area:</span></span>  <br/> |<span data-ttu-id="21929-115">联系人</span><span class="sxs-lookup"><span data-stu-id="21929-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="21929-116">备注</span><span class="sxs-lookup"><span data-stu-id="21929-116">Remarks</span></span>

<span data-ttu-id="21929-117">此属性指定的约会必须使用 **dispidApptStateFlags** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)) 、dispidContactLinkSearchKey ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)) 和 **dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) 属性链接到此联系人，如 [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中指定。 </span><span class="sxs-lookup"><span data-stu-id="21929-117">The appointment this is specified by this property must be linked to this contact by using the **dispidApptStateFlags** ([PidLidContactLinkEntry](pidlidcontactlinkentry-canonical-property.md)), **dispidContactLinkSearchKey** ([PidLidContactLinkSearchKey](pidlidcontactlinksearchkey-canonical-property.md)), and **dispidContactLinkName** ([PidLidContactLinkName](pidlidcontactlinkname-canonical-property.md)) properties, as specified in [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="21929-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="21929-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="21929-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="21929-119">Protocol specifications</span></span>

<span data-ttu-id="21929-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="21929-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="21929-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="21929-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="21929-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="21929-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="21929-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="21929-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="21929-124">头文件</span><span class="sxs-lookup"><span data-stu-id="21929-124">Header files</span></span>

<span data-ttu-id="21929-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="21929-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="21929-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="21929-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="21929-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21929-127">See also</span></span>



[<span data-ttu-id="21929-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="21929-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="21929-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="21929-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="21929-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="21929-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="21929-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="21929-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

