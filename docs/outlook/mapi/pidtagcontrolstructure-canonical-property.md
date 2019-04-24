---
title: PidTagControlStructure 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlStructure
api_type:
- HeaderDef
ms.assetid: 02910389-b346-431c-a282-dedbc9f7dfc6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cf91620042f916d51f27be50d15f72db537ad5f7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335243"
---
# <a name="pidtagcontrolstructure-canonical-property"></a><span data-ttu-id="f0f9a-103">PidTagControlStructure 规范属性</span><span class="sxs-lookup"><span data-stu-id="f0f9a-103">PidTagControlStructure Canonical Property</span></span>

  
  
<span data-ttu-id="f0f9a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0f9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0f9a-105">包含指向对话框中使用的控件的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="f0f9a-105">Contains a pointer to a structure for a control used in a dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f0f9a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f0f9a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f0f9a-107">PR_CONTROL_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="f0f9a-107">PR_CONTROL_STRUCTURE</span></span>  <br/> |
|<span data-ttu-id="f0f9a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f0f9a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f0f9a-109">0x3F01</span><span class="sxs-lookup"><span data-stu-id="f0f9a-109">0x3F01</span></span>  <br/> |
|<span data-ttu-id="f0f9a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f0f9a-110">Data type:</span></span>  <br/> |<span data-ttu-id="f0f9a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f0f9a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f0f9a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f0f9a-112">Area:</span></span>  <br/> |<span data-ttu-id="f0f9a-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="f0f9a-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f0f9a-114">注解</span><span class="sxs-lookup"><span data-stu-id="f0f9a-114">Remarks</span></span>

<span data-ttu-id="f0f9a-115">此属性表示一个长指针, 该指针被转换为控件结构之一。</span><span class="sxs-lookup"><span data-stu-id="f0f9a-115">This property represents a long pointer that is cast to one of the control structures.</span></span> <span data-ttu-id="f0f9a-116">控制结构包括:</span><span class="sxs-lookup"><span data-stu-id="f0f9a-116">The control structures include:</span></span>
  
|||
|:-----|:-----|
|[<span data-ttu-id="f0f9a-117">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="f0f9a-117">DTBLBUTTON</span></span>](dtblbutton.md) <br/> |[<span data-ttu-id="f0f9a-118">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-118">DTBLCHECKBOX</span></span>](dtblcheckbox.md) <br/> |
|[<span data-ttu-id="f0f9a-119">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-119">DTBLCOMBOBOX</span></span>](dtblcombobox.md) <br/> |[<span data-ttu-id="f0f9a-120">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-120">DTBLDDLBX</span></span>](dtblddlbx.md) <br/> |
|[<span data-ttu-id="f0f9a-121">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="f0f9a-121">DTBLEDIT</span></span>](dtbledit.md) <br/> |[<span data-ttu-id="f0f9a-122">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-122">DTBLGROUPBOX</span></span>](dtblgroupbox.md) <br/> |
|[<span data-ttu-id="f0f9a-123">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="f0f9a-123">DTBLLABEL</span></span>](dtbllabel.md) <br/> |[<span data-ttu-id="f0f9a-124">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-124">DTBLLBX</span></span>](dtbllbx.md) <br/> |
|[<span data-ttu-id="f0f9a-125">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-125">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md) <br/> |[<span data-ttu-id="f0f9a-126">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="f0f9a-126">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md) <br/> |
|[<span data-ttu-id="f0f9a-127">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="f0f9a-127">DTBLPAGE</span></span>](dtblpage.md) <br/> |[<span data-ttu-id="f0f9a-128">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="f0f9a-128">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md) <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="f0f9a-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="f0f9a-129">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f0f9a-130">头文件</span><span class="sxs-lookup"><span data-stu-id="f0f9a-130">Header files</span></span>

<span data-ttu-id="f0f9a-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f0f9a-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="f0f9a-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f0f9a-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="f0f9a-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="f0f9a-133">Mapitags.h</span></span>
  
> <span data-ttu-id="f0f9a-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f0f9a-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f0f9a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f9a-135">See also</span></span>



[<span data-ttu-id="f0f9a-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f0f9a-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f0f9a-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f0f9a-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f0f9a-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f0f9a-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f0f9a-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f0f9a-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

