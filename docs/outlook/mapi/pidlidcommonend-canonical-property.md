---
title: PidLidCommonEnd 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCommonEnd
api_type:
- COM
ms.assetid: c89f388a-1585-4bed-91b4-1b0c268292f3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97d6ef6343cedb6fbed93cccda9f65476bb73f4f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345498"
---
# <a name="pidlidcommonend-canonical-property"></a><span data-ttu-id="d995a-103">PidLidCommonEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="d995a-103">PidLidCommonEnd Canonical Property</span></span>

  
  
<span data-ttu-id="d995a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d995a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d995a-105">表示邮件的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d995a-105">Represents the end date and time of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d995a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d995a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d995a-107">dispidCommonEnd</span><span class="sxs-lookup"><span data-stu-id="d995a-107">dispidCommonEnd</span></span>  <br/> |
|<span data-ttu-id="d995a-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="d995a-108">Property set:</span></span>  <br/> |<span data-ttu-id="d995a-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="d995a-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="d995a-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="d995a-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d995a-111">0x00008517</span><span class="sxs-lookup"><span data-stu-id="d995a-111">0x00008517</span></span>  <br/> |
|<span data-ttu-id="d995a-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d995a-112">Data type:</span></span>  <br/> |<span data-ttu-id="d995a-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d995a-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="d995a-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d995a-114">Area:</span></span>  <br/> |<span data-ttu-id="d995a-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="d995a-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d995a-116">备注</span><span class="sxs-lookup"><span data-stu-id="d995a-116">Remarks</span></span>

<span data-ttu-id="d995a-117">此属性指示项目的结束时间。</span><span class="sxs-lookup"><span data-stu-id="d995a-117">This property indicates the end time for an item.</span></span> <span data-ttu-id="d995a-118">它必须大于或等于 **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="d995a-118">It must be greater than or equal to the value of the **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="d995a-119">此值必须是协调世界时 (UTC) 相当于 **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d995a-119">This value must be the Coordinated Universal Time (UTC) equivalent of the **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d995a-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="d995a-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d995a-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="d995a-121">Protocol specifications</span></span>

<span data-ttu-id="d995a-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d995a-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d995a-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="d995a-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d995a-124">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d995a-124">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d995a-125">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="d995a-125">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="d995a-126">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d995a-126">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d995a-127">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d995a-127">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d995a-128">头文件</span><span class="sxs-lookup"><span data-stu-id="d995a-128">Header files</span></span>

<span data-ttu-id="d995a-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d995a-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="d995a-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d995a-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d995a-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d995a-131">See also</span></span>



[<span data-ttu-id="d995a-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d995a-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d995a-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d995a-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d995a-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d995a-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d995a-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d995a-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

