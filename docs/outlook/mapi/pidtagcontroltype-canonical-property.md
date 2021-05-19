---
title: PidTagControlType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagControlType
api_type:
- HeaderDef
ms.assetid: 7728fa2f-4a59-4e86-90f1-4384824598aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7bdb02f72ba14a36c8a4c218cd5f0631e7145e6a
ms.sourcegitcommit: 0419850d5c1b3439d9da59070201fb4952ca5d07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734201"
---
# <a name="pidtagcontroltype-canonical-property"></a><span data-ttu-id="ee821-103">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="ee821-103">PidTagControlType Canonical Property</span></span>

  
  
<span data-ttu-id="ee821-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ee821-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ee821-105">包含一个值，该值指示对话框中使用的控件的控件类型。</span><span class="sxs-lookup"><span data-stu-id="ee821-105">Contains a value indicating a control type for a control used in a dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ee821-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ee821-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ee821-107">PR_CONTROL_TYPE</span><span class="sxs-lookup"><span data-stu-id="ee821-107">PR_CONTROL_TYPE</span></span>  <br/> |
|<span data-ttu-id="ee821-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ee821-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ee821-109">0x3F02</span><span class="sxs-lookup"><span data-stu-id="ee821-109">0x3F02</span></span>  <br/> |
|<span data-ttu-id="ee821-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ee821-110">Data type:</span></span>  <br/> |<span data-ttu-id="ee821-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ee821-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ee821-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ee821-112">Area:</span></span>  <br/> |<span data-ttu-id="ee821-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="ee821-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ee821-114">备注</span><span class="sxs-lookup"><span data-stu-id="ee821-114">Remarks</span></span>

<span data-ttu-id="ee821-115">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ee821-115">This property can have exactly one of the following values:</span></span>
    
<span data-ttu-id="ee821-116">DTCT_LABEL (0x00000000) </span><span class="sxs-lookup"><span data-stu-id="ee821-116">DTCT_LABEL (0x00000000)</span></span>
  
> <span data-ttu-id="ee821-117">对话框标签。</span><span class="sxs-lookup"><span data-stu-id="ee821-117">A dialog label.</span></span>
   
<span data-ttu-id="ee821-118">DTCT_EDIT (0x00000001) </span><span class="sxs-lookup"><span data-stu-id="ee821-118">DTCT_EDIT (0x00000001)</span></span>
  
> <span data-ttu-id="ee821-119">对话框编辑文本框。</span><span class="sxs-lookup"><span data-stu-id="ee821-119">A dialog edit text box.</span></span>

<span data-ttu-id="ee821-120">DTCT_LBX (0x00000002) </span><span class="sxs-lookup"><span data-stu-id="ee821-120">DTCT_LBX (0x00000002)</span></span>
  
> <span data-ttu-id="ee821-121">对话框列表框。</span><span class="sxs-lookup"><span data-stu-id="ee821-121">A dialog list box.</span></span>
    
<span data-ttu-id="ee821-122">DTCT_COMBOBOX (0x00000003) </span><span class="sxs-lookup"><span data-stu-id="ee821-122">DTCT_COMBOBOX (0x00000003)</span></span>
  
> <span data-ttu-id="ee821-123">对话框组合框。</span><span class="sxs-lookup"><span data-stu-id="ee821-123">A dialog combo box.</span></span>

<span data-ttu-id="ee821-124">DTCT_DDLBX (0x00000004) </span><span class="sxs-lookup"><span data-stu-id="ee821-124">DTCT_DDLBX (0x00000004)</span></span>
  
> <span data-ttu-id="ee821-125">对话框下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="ee821-125">A dialog drop-down list box.</span></span>

<span data-ttu-id="ee821-126">DTCT_CHECKBOX (0x00000005) </span><span class="sxs-lookup"><span data-stu-id="ee821-126">DTCT_CHECKBOX (0x00000005)</span></span>
  
> <span data-ttu-id="ee821-127">对话框。</span><span class="sxs-lookup"><span data-stu-id="ee821-127">A dialog check box.</span></span>

<span data-ttu-id="ee821-128">DTCT_GROUPBOX (0x00000006) </span><span class="sxs-lookup"><span data-stu-id="ee821-128">DTCT_GROUPBOX (0x00000006)</span></span>
  
> <span data-ttu-id="ee821-129">对话框组框。</span><span class="sxs-lookup"><span data-stu-id="ee821-129">A dialog group box.</span></span>
  
<span data-ttu-id="ee821-130">DTCT_BUTTON (0x00000007) </span><span class="sxs-lookup"><span data-stu-id="ee821-130">DTCT_BUTTON (0x00000007)</span></span>
  
> <span data-ttu-id="ee821-131">对话框按钮控件。</span><span class="sxs-lookup"><span data-stu-id="ee821-131">A dialog button control.</span></span>
    
<span data-ttu-id="ee821-132">DTCT_PAGE (0x00000008) </span><span class="sxs-lookup"><span data-stu-id="ee821-132">DTCT_PAGE (0x00000008)</span></span>
  
> <span data-ttu-id="ee821-133">对话框选项卡式页面。</span><span class="sxs-lookup"><span data-stu-id="ee821-133">A dialog tabbed page.</span></span>
    
<span data-ttu-id="ee821-134">DTCT_RADIOBUTTON (0x00000009) </span><span class="sxs-lookup"><span data-stu-id="ee821-134">DTCT_RADIOBUTTON (0x00000009)</span></span>
  
> <span data-ttu-id="ee821-135">对话框单选按钮。</span><span class="sxs-lookup"><span data-stu-id="ee821-135">A dialog radio button.</span></span>
    
<span data-ttu-id="ee821-136">DTCT_MVLISTBOX (0x0000000B) </span><span class="sxs-lookup"><span data-stu-id="ee821-136">DTCT_MVLISTBOX (0x0000000B)</span></span>
  
> <span data-ttu-id="ee821-137">由 string 类型的多值属性填充的多值列表框。</span><span class="sxs-lookup"><span data-stu-id="ee821-137">A multivalued list box populated by a multivalued property of type string.</span></span>
    
<span data-ttu-id="ee821-138">DTCT_MVDDLBX (0x0000000C) </span><span class="sxs-lookup"><span data-stu-id="ee821-138">DTCT_MVDDLBX (0x0000000C)</span></span>
  
> <span data-ttu-id="ee821-139">由 string 类型的多值属性填充的多值下拉列表框。</span><span class="sxs-lookup"><span data-stu-id="ee821-139">A multivalued drop-down list box populated by a multivalued property of type string.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="ee821-140">相关资源</span><span class="sxs-lookup"><span data-stu-id="ee821-140">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ee821-141">头文件</span><span class="sxs-lookup"><span data-stu-id="ee821-141">Header files</span></span>

<span data-ttu-id="ee821-142">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ee821-142">Mapidefs.h</span></span>
  
> <span data-ttu-id="ee821-143">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ee821-143">Provides data type definitions.</span></span>
    
<span data-ttu-id="ee821-144">mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ee821-144">mapitags.h</span></span>
  
> <span data-ttu-id="ee821-145">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ee821-145">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ee821-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee821-146">See also</span></span>



[<span data-ttu-id="ee821-147">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ee821-147">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ee821-148">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ee821-148">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ee821-149">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ee821-149">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ee821-150">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ee821-150">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

