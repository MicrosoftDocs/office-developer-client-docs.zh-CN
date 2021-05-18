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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412945"
---
# <a name="pidtagcontrolstructure-canonical-property"></a><span data-ttu-id="1f598-103">PidTagControlStructure 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f598-103">PidTagControlStructure Canonical Property</span></span>

  
  
<span data-ttu-id="1f598-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f598-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f598-105">包含指向对话框中使用的控件的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="1f598-105">Contains a pointer to a structure for a control used in a dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1f598-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1f598-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f598-107">PR_CONTROL_STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="1f598-107">PR_CONTROL_STRUCTURE</span></span>  <br/> |
|<span data-ttu-id="1f598-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1f598-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1f598-109">0x3F01</span><span class="sxs-lookup"><span data-stu-id="1f598-109">0x3F01</span></span>  <br/> |
|<span data-ttu-id="1f598-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f598-110">Data type:</span></span>  <br/> |<span data-ttu-id="1f598-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1f598-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="1f598-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1f598-112">Area:</span></span>  <br/> |<span data-ttu-id="1f598-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="1f598-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f598-114">备注</span><span class="sxs-lookup"><span data-stu-id="1f598-114">Remarks</span></span>

<span data-ttu-id="1f598-115">此属性表示一个长指针，该指针将强制转换到控件结构之一。</span><span class="sxs-lookup"><span data-stu-id="1f598-115">This property represents a long pointer that is cast to one of the control structures.</span></span> <span data-ttu-id="1f598-116">控制结构包括：</span><span class="sxs-lookup"><span data-stu-id="1f598-116">The control structures include:</span></span>
  
|||
|:-----|:-----|
|[<span data-ttu-id="1f598-117">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="1f598-117">DTBLBUTTON</span></span>](dtblbutton.md) <br/> |[<span data-ttu-id="1f598-118">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="1f598-118">DTBLCHECKBOX</span></span>](dtblcheckbox.md) <br/> |
|[<span data-ttu-id="1f598-119">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="1f598-119">DTBLCOMBOBOX</span></span>](dtblcombobox.md) <br/> |[<span data-ttu-id="1f598-120">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="1f598-120">DTBLDDLBX</span></span>](dtblddlbx.md) <br/> |
|[<span data-ttu-id="1f598-121">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="1f598-121">DTBLEDIT</span></span>](dtbledit.md) <br/> |[<span data-ttu-id="1f598-122">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="1f598-122">DTBLGROUPBOX</span></span>](dtblgroupbox.md) <br/> |
|[<span data-ttu-id="1f598-123">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="1f598-123">DTBLLABEL</span></span>](dtbllabel.md) <br/> |[<span data-ttu-id="1f598-124">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="1f598-124">DTBLLBX</span></span>](dtbllbx.md) <br/> |
|[<span data-ttu-id="1f598-125">DTBLMVDDLBOX</span><span class="sxs-lookup"><span data-stu-id="1f598-125">DTBLMVDDLBOX</span></span>](dtblmvddlbox.md) <br/> |[<span data-ttu-id="1f598-126">DTBLMVLISTBOX</span><span class="sxs-lookup"><span data-stu-id="1f598-126">DTBLMVLISTBOX</span></span>](dtblmvlistbox.md) <br/> |
|[<span data-ttu-id="1f598-127">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="1f598-127">DTBLPAGE</span></span>](dtblpage.md) <br/> |[<span data-ttu-id="1f598-128">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="1f598-128">DTBLRADIOBUTTON</span></span>](dtblradiobutton.md) <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="1f598-129">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f598-129">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1f598-130">头文件</span><span class="sxs-lookup"><span data-stu-id="1f598-130">Header files</span></span>

<span data-ttu-id="1f598-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f598-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f598-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f598-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="1f598-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1f598-133">Mapitags.h</span></span>
  
> <span data-ttu-id="1f598-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1f598-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f598-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f598-135">See also</span></span>



[<span data-ttu-id="1f598-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f598-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f598-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f598-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f598-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1f598-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f598-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f598-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

