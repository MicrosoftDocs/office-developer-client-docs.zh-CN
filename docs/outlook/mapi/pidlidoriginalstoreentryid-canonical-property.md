---
title: PidLidOriginalStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOriginalStoreEntryId
api_type:
- COM
ms.assetid: 1b1fc008-9cd5-49f6-9f91-b59e305a1e82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 83ca47d0b7e10bff4b2274ef8a8c7dd7b5421d54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359113"
---
# <a name="pidlidoriginalstoreentryid-canonical-property"></a><span data-ttu-id="7527f-103">PidLidOriginalStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="7527f-103">PidLidOriginalStoreEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="7527f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7527f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7527f-105">指定委派者存储的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="7527f-105">Specifies the entry ID of the delegator's store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7527f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7527f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7527f-107">dispidOrigStoreEid</span><span class="sxs-lookup"><span data-stu-id="7527f-107">dispidOrigStoreEid</span></span>  <br/> |
|<span data-ttu-id="7527f-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="7527f-108">Property set:</span></span>  <br/> |<span data-ttu-id="7527f-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="7527f-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="7527f-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="7527f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7527f-111">0x00008237</span><span class="sxs-lookup"><span data-stu-id="7527f-111">0x00008237</span></span>  <br/> |
|<span data-ttu-id="7527f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7527f-112">Data type:</span></span>  <br/> |<span data-ttu-id="7527f-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="7527f-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="7527f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7527f-114">Area:</span></span>  <br/> |<span data-ttu-id="7527f-115">会议</span><span class="sxs-lookup"><span data-stu-id="7527f-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7527f-116">备注</span><span class="sxs-lookup"><span data-stu-id="7527f-116">Remarks</span></span>

<span data-ttu-id="7527f-117">应在已由代理创建或更新的会议对象上设置此属性。</span><span class="sxs-lookup"><span data-stu-id="7527f-117">This property should be set on meeting objects which have been created or updated by a delegate.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7527f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7527f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7527f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7527f-119">Protocol specifications</span></span>

<span data-ttu-id="7527f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7527f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7527f-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="7527f-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7527f-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7527f-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7527f-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7527f-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7527f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7527f-124">Header files</span></span>

<span data-ttu-id="7527f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7527f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7527f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7527f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7527f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7527f-127">See also</span></span>



[<span data-ttu-id="7527f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7527f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7527f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7527f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7527f-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7527f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7527f-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7527f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

