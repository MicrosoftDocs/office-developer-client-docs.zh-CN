---
title: PidTagAccessLevel 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAccessLevel
api_type:
- HeaderDef
ms.assetid: 8f7119c7-ffc3-47cf-aa1b-b4e56bcc5a24
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddb667715903656291a21ebb835690768146ee9c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575223"
---
# <a name="pidtagaccesslevel-canonical-property"></a><span data-ttu-id="83c53-103">PidTagAccessLevel 规范属性</span><span class="sxs-lookup"><span data-stu-id="83c53-103">PidTagAccessLevel Canonical Property</span></span>

  
  
<span data-ttu-id="83c53-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="83c53-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="83c53-105">指示对对象的客户端的访问级别。</span><span class="sxs-lookup"><span data-stu-id="83c53-105">Indicates the client's access level to the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="83c53-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="83c53-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="83c53-107">PR_ACCESS_LEVEL</span><span class="sxs-lookup"><span data-stu-id="83c53-107">PR_ACCESS_LEVEL</span></span>  <br/> |
|<span data-ttu-id="83c53-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="83c53-108">Identifier:</span></span>  <br/> |<span data-ttu-id="83c53-109">0x0FF7</span><span class="sxs-lookup"><span data-stu-id="83c53-109">0x0FF7</span></span>  <br/> |
|<span data-ttu-id="83c53-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="83c53-110">Data type:</span></span>  <br/> |<span data-ttu-id="83c53-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="83c53-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="83c53-112">区域：</span><span class="sxs-lookup"><span data-stu-id="83c53-112">Area:</span></span>  <br/> |<span data-ttu-id="83c53-113">访问控件属性</span><span class="sxs-lookup"><span data-stu-id="83c53-113">Access Control Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="83c53-114">注解</span><span class="sxs-lookup"><span data-stu-id="83c53-114">Remarks</span></span>

<span data-ttu-id="83c53-115">此属性是只读的客户端。</span><span class="sxs-lookup"><span data-stu-id="83c53-115">This property is read-only for the client.</span></span> <span data-ttu-id="83c53-116">它必须是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="83c53-116">It must be one of the following values:</span></span>
  
|<span data-ttu-id="83c53-117">**值**</span><span class="sxs-lookup"><span data-stu-id="83c53-117">**Value**</span></span>|<span data-ttu-id="83c53-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="83c53-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83c53-119">0x00000000</span><span class="sxs-lookup"><span data-stu-id="83c53-119">0x00000000</span></span>  <br/> |<span data-ttu-id="83c53-120">只读</span><span class="sxs-lookup"><span data-stu-id="83c53-120">Read-Only</span></span>  <br/> |
|<span data-ttu-id="83c53-121">0x00000001</span><span class="sxs-lookup"><span data-stu-id="83c53-121">0x00000001</span></span>  <br/> |<span data-ttu-id="83c53-122">Modify</span><span class="sxs-lookup"><span data-stu-id="83c53-122">Modify</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="83c53-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="83c53-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="83c53-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="83c53-124">Protocol specifications</span></span>

<span data-ttu-id="83c53-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="83c53-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="83c53-126">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="83c53-126">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="83c53-127">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="83c53-127">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="83c53-128">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="83c53-128">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="83c53-129">头文件</span><span class="sxs-lookup"><span data-stu-id="83c53-129">Header files</span></span>

<span data-ttu-id="83c53-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="83c53-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="83c53-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="83c53-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="83c53-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="83c53-132">Mapitags.h</span></span>
  
> <span data-ttu-id="83c53-133">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="83c53-133">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="83c53-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83c53-134">See also</span></span>



[<span data-ttu-id="83c53-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="83c53-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="83c53-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="83c53-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="83c53-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="83c53-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="83c53-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="83c53-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

