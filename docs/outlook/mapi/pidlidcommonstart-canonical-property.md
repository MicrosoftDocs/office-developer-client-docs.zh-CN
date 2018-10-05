---
title: PidLidCommonStart 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCommonStart
api_type:
- COM
ms.assetid: d999852d-ce98-4c3c-a772-87f5db4aa04e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ec7c213d7eec9ab0ef5766442e3de59a24811d37
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398694"
---
# <a name="pidlidcommonstart-canonical-property"></a><span data-ttu-id="acbb3-103">PidLidCommonStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="acbb3-103">PidLidCommonStart Canonical Property</span></span>

  
  
<span data-ttu-id="acbb3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="acbb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="acbb3-105">表示的开始日期和时间一条消息。</span><span class="sxs-lookup"><span data-stu-id="acbb3-105">Represents the start date and time of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="acbb3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="acbb3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="acbb3-107">dispidCommonStart</span><span class="sxs-lookup"><span data-stu-id="acbb3-107">dispidCommonStart</span></span>  <br/> |
|<span data-ttu-id="acbb3-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="acbb3-108">Property set:</span></span>  <br/> |<span data-ttu-id="acbb3-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="acbb3-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="acbb3-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="acbb3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="acbb3-111">0x00008516</span><span class="sxs-lookup"><span data-stu-id="acbb3-111">0x00008516</span></span>  <br/> |
|<span data-ttu-id="acbb3-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="acbb3-112">Data type:</span></span>  <br/> |<span data-ttu-id="acbb3-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="acbb3-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="acbb3-114">区域：</span><span class="sxs-lookup"><span data-stu-id="acbb3-114">Area:</span></span>  <br/> |<span data-ttu-id="acbb3-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="acbb3-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="acbb3-116">说明</span><span class="sxs-lookup"><span data-stu-id="acbb3-116">Remarks</span></span>

<span data-ttu-id="acbb3-117">此属性指示项目的开始时间。</span><span class="sxs-lookup"><span data-stu-id="acbb3-117">This property indicates the start time for an item.</span></span> <span data-ttu-id="acbb3-118">它必须小于或等于**dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="acbb3-118">It must be less than or equal to the value of the **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="acbb3-119">此属性的值必须是协调世界时 (UTC) 相当于**dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="acbb3-119">The value of this property must be the Coordinated Universal Time (UTC) equivalent of the **dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="acbb3-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="acbb3-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="acbb3-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="acbb3-121">Protocol specifications</span></span>

<span data-ttu-id="acbb3-122">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="acbb3-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="acbb3-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="acbb3-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="acbb3-124">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="acbb3-124">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="acbb3-125">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="acbb3-125">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="acbb3-126">[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="acbb3-126">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="acbb3-127">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="acbb3-127">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="acbb3-128">头文件</span><span class="sxs-lookup"><span data-stu-id="acbb3-128">Header files</span></span>

<span data-ttu-id="acbb3-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="acbb3-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="acbb3-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="acbb3-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="acbb3-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acbb3-131">See also</span></span>



[<span data-ttu-id="acbb3-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="acbb3-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="acbb3-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="acbb3-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="acbb3-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="acbb3-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="acbb3-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="acbb3-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

