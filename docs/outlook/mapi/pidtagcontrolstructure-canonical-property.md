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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e531c986ef6de2eccca446f5d560290fed831c21
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777498"
---
# <a name="pidtagcontrolstructure-canonical-property"></a><span data-ttu-id="ac41f-103">PidTagControlStructure 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac41f-103">PidTagControlStructure Canonical Property</span></span>

  
  
<span data-ttu-id="ac41f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac41f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac41f-105">包含指向用于在对话框中使用的控件的结构。</span><span class="sxs-lookup"><span data-stu-id="ac41f-105">Contains a pointer to a structure for a control used in a dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ac41f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ac41f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ac41f-107">PR_CONTROL_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="ac41f-107">PR_CONTROL_STRUCTURE</span></span>  <br/> |
|<span data-ttu-id="ac41f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ac41f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ac41f-109">0x3F01</span><span class="sxs-lookup"><span data-stu-id="ac41f-109">0x3F01</span></span>  <br/> |
|<span data-ttu-id="ac41f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ac41f-110">Data type:</span></span>  <br/> |<span data-ttu-id="ac41f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ac41f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ac41f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ac41f-112">Area:</span></span>  <br/> |<span data-ttu-id="ac41f-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="ac41f-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac41f-114">备注</span><span class="sxs-lookup"><span data-stu-id="ac41f-114">Remarks</span></span>

<span data-ttu-id="ac41f-115">此属性表示被强制转换为控制结构之一的 long 指针。</span><span class="sxs-lookup"><span data-stu-id="ac41f-115">This property represents a long pointer that is cast to one of the control structures.</span></span> <span data-ttu-id="ac41f-116">控制结构包括：</span><span class="sxs-lookup"><span data-stu-id="ac41f-116">The control structures include:</span></span>
  
|||
|:-----|:-----|
|[<span data-ttu-id="ac41f-117">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="ac41f-117">DTBLBUTTON</span></span>](dtblbutton.md) <br/> |[<span data-ttu-id="ac41f-118">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="ac41f-118">DTBLCHECKBOX</span></span>](dtblcheckbox.md) <br/> |
|[<span data-ttu-id="ac41f-119">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="ac41f-119">DTBLCOMBOBOX</span></span>](dtblcombobox.md) <br/> |[<span data-ttu-id="ac41f-120">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="ac41f-120">DTBLDDLBX</span></span>](dtblddlbx.md) <br/> |
|[<span data-ttu-id="ac41f-121">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="ac41f-121">DTBLEDIT</span></span>](dtbledit.md) <br/> |[<span data-ttu-id="ac41f-122">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="ac41f-122">DTBLGROUPBOX</span></span>](dtblgroupbox.md) <br/> |
|[<span data-ttu-id="ac41f-123">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="ac41f-123">DTBLLABEL</span></span>](dtbllabel.md) <br/> |[<span data-ttu-id="ac41f-124">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="ac41f-124">DTBLLBX</span></span>](dtbllbx.md) <br/> |
|[<span data-ttu-id="ac41f-125">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="ac41f-125">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md) <br/> |[<span data-ttu-id="ac41f-126">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="ac41f-126">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md) <br/> |
|[<span data-ttu-id="ac41f-127">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="ac41f-127">DTBLPAGE</span></span>](dtblpage.md) <br/> |[<span data-ttu-id="ac41f-128">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="ac41f-128">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md) <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ac41f-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="ac41f-129">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ac41f-130">头文件</span><span class="sxs-lookup"><span data-stu-id="ac41f-130">Header files</span></span>

<span data-ttu-id="ac41f-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ac41f-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="ac41f-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ac41f-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="ac41f-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ac41f-133">Mapitags.h</span></span>
  
> <span data-ttu-id="ac41f-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ac41f-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac41f-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac41f-135">See also</span></span>



[<span data-ttu-id="ac41f-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ac41f-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ac41f-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac41f-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ac41f-138">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac41f-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ac41f-139">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac41f-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
