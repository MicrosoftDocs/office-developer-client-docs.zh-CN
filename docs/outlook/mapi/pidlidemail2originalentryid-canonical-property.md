---
title: PidLidEmail2OriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail2OriginalEntryId
api_type:
- COM
ms.assetid: 10d45a99-54aa-4721-8847-1c7033a8a5b5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08495ef0a38fda52c0cd011277995cf21ea756f7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564470"
---
# <a name="pidlidemail2originalentryid-canonical-property"></a><span data-ttu-id="3d882-103">PidLidEmail2OriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d882-103">PidLidEmail2OriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="3d882-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d882-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d882-105">指定对象对应于第二个电子邮件地址的**EntryId** 。</span><span class="sxs-lookup"><span data-stu-id="3d882-105">Specifies the **EntryId** of the object that corresponds to the second email address.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3d882-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3d882-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3d882-107">dispidEmail2OriginalEntryID</span><span class="sxs-lookup"><span data-stu-id="3d882-107">dispidEmail2OriginalEntryID</span></span>  <br/> |
|<span data-ttu-id="3d882-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="3d882-108">Property set:</span></span>  <br/> |<span data-ttu-id="3d882-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="3d882-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="3d882-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="3d882-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3d882-111">0x00008095</span><span class="sxs-lookup"><span data-stu-id="3d882-111">0x00008095</span></span>  <br/> |
|<span data-ttu-id="3d882-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3d882-112">Data type:</span></span>  <br/> |<span data-ttu-id="3d882-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="3d882-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="3d882-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3d882-114">Area:</span></span>  <br/> |<span data-ttu-id="3d882-115">联系人</span><span class="sxs-lookup"><span data-stu-id="3d882-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d882-116">注解</span><span class="sxs-lookup"><span data-stu-id="3d882-116">Remarks</span></span>

<span data-ttu-id="3d882-117">此属性的值必须是此电子通讯一次性**EntryId**或有效的通讯簿对象**EntryId**。</span><span class="sxs-lookup"><span data-stu-id="3d882-117">The value of this property must be either a one-off **EntryId** for this electronic address or a valid Address Book object **EntryId**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3d882-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="3d882-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3d882-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="3d882-119">Protocol specifications</span></span>

<span data-ttu-id="3d882-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d882-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3d882-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3d882-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3d882-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3d882-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3d882-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3d882-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3d882-124">头文件</span><span class="sxs-lookup"><span data-stu-id="3d882-124">Header files</span></span>

<span data-ttu-id="3d882-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3d882-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="3d882-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3d882-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d882-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d882-127">See also</span></span>



[<span data-ttu-id="3d882-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3d882-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3d882-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d882-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3d882-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3d882-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3d882-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3d882-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

