---
title: THEMECBV 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ef62f63f-b2ce-4d12-a294-93dbdc9a869d
description: 返回一个 RGB 值或一个整数, 表示文档的调色板中的索引, 其中的颜色 (数字) 以参数形式传入, 并由活动主题的渐变设置中存储的指定淡色或底纹值修改。
ms.openlocfilehash: 014dc04c5114e296cd2226f3cf04dfb729817578
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332261"
---
# <a name="themecbv-function"></a><span data-ttu-id="f97b1-103">THEMECBV 函数</span><span class="sxs-lookup"><span data-stu-id="f97b1-103">THEMECBV Function</span></span>

<span data-ttu-id="f97b1-104">返回一个 RGB 值或一个整数, 表示文档的调色板中的索引, 其中的颜色 (数字) 以参数形式传入, 并由活动主题的渐变设置中存储的指定淡色或底纹值修改。</span><span class="sxs-lookup"><span data-stu-id="f97b1-104">Returns an RGB value or an integer that represents an index in the document's color palette, where the color (number) passed in as an argument has been modified by the specified tint or shade value stored in the gradient settings of the active theme.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="f97b1-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="f97b1-105">Version Information</span></span>

<span data-ttu-id="f97b1-106">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="f97b1-106">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f97b1-107">语法</span><span class="sxs-lookup"><span data-stu-id="f97b1-107">Syntax</span></span>

 <span data-ttu-id="f97b1-108">**THEMECBV**( _color_, _gradient_stop_number_)</span><span class="sxs-lookup"><span data-stu-id="f97b1-108">**THEMECBV**( _color_,  _gradient_stop_number_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="f97b1-109">参数</span><span class="sxs-lookup"><span data-stu-id="f97b1-109">Parameters</span></span>

|<span data-ttu-id="f97b1-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="f97b1-110">**Name**</span></span>|<span data-ttu-id="f97b1-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="f97b1-111">**Required/Optional**</span></span>|<span data-ttu-id="f97b1-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f97b1-112">**Data Type**</span></span>|<span data-ttu-id="f97b1-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="f97b1-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f97b1-114">_color_</span><span class="sxs-lookup"><span data-stu-id="f97b1-114">_color_</span></span> <br/> |<span data-ttu-id="f97b1-115">必需</span><span class="sxs-lookup"><span data-stu-id="f97b1-115">Required</span></span>  <br/> |<span data-ttu-id="f97b1-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="f97b1-116">**Number**</span></span> <br/> |<span data-ttu-id="f97b1-117">表示文档调色板中的索引的数字。</span><span class="sxs-lookup"><span data-stu-id="f97b1-117">A number representing an index in the document's color palette.</span></span>  <br/> |
| <span data-ttu-id="f97b1-118">_gradient_stop_number_</span><span class="sxs-lookup"><span data-stu-id="f97b1-118">_gradient_stop_number_</span></span> <br/> |<span data-ttu-id="f97b1-119">必需</span><span class="sxs-lookup"><span data-stu-id="f97b1-119">Required</span></span>  <br/> |<span data-ttu-id="f97b1-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="f97b1-120">**Number**</span></span> <br/> |<span data-ttu-id="f97b1-121">存储在活动主题的渐变设置中以应用于该颜色的渐变停止点 (淡色或底纹)。</span><span class="sxs-lookup"><span data-stu-id="f97b1-121">The gradient stop (tint or shade) stored in the gradient settings of the active theme to apply to the color.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="f97b1-122">返回值</span><span class="sxs-lookup"><span data-stu-id="f97b1-122">Return value</span></span>

 <span data-ttu-id="f97b1-123">**Number**</span><span class="sxs-lookup"><span data-stu-id="f97b1-123">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f97b1-124">注解</span><span class="sxs-lookup"><span data-stu-id="f97b1-124">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="f97b1-125">如果分配给形状的 QuickStyle 没有渐变, 则 THEMECBV 函数对作为参数传入的颜色不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f97b1-125">The THEMECBV function does nothing to the color passed in as an argument if the QuickStyle that is assigned to the shape does not have a gradient.</span></span> 
  
<span data-ttu-id="f97b1-126">主题中的渐变设置是一系列与 "变亮" (淡色) 或 "变暗" (底纹) 相对应的编号渐变停止点。</span><span class="sxs-lookup"><span data-stu-id="f97b1-126">The gradient settings in a theme are a series of numbered gradient stops that correspond to a "lightening" (tint) or "darkening" (shade).</span></span> <span data-ttu-id="f97b1-127">这些底纹和色调应用于基色, 以创建渐变颜色效果。</span><span class="sxs-lookup"><span data-stu-id="f97b1-127">These shades and tints are applied to a base color to create a gradient color effect.</span></span>
  
<span data-ttu-id="f97b1-128">**THEMECBV**函数采用颜色输入, 并在指定的渐变光圈的淡色或底纹修改后输出颜色。</span><span class="sxs-lookup"><span data-stu-id="f97b1-128">The **THEMECBV** function takes a color input and outputs the color after it has been modified by the tint or shade of the specified gradient stop.</span></span> <span data-ttu-id="f97b1-129">如果当前快速样式包含渐变填充, 则 "淡色" 和 "底纹" 来自主题的定义。</span><span class="sxs-lookup"><span data-stu-id="f97b1-129">The tints and shades come from the theme's definition, if the current quick style contains a gradient fill.</span></span> <span data-ttu-id="f97b1-130">如果活动快速样式未指定渐变填充或形状设置为 "无主题", 则此公式只返回为第一个参数传入的颜色。</span><span class="sxs-lookup"><span data-stu-id="f97b1-130">If the active Quick Style does not specify a gradient fill or the shape is set to No Theme, then this formula simply returns the color that was passed in for the first argument.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f97b1-131">示例</span><span class="sxs-lookup"><span data-stu-id="f97b1-131">Example</span></span>

 `THEMECBV(FillForegnd, 5)`
  
<span data-ttu-id="f97b1-132">返回通过将渐变的第五个渐变停止点中的淡色或底纹应用于**FillForegnd**单元格中指定的颜色而创建的颜色。</span><span class="sxs-lookup"><span data-stu-id="f97b1-132">Returns the color created by applying the tint or shade in the fifth gradient stop of the gradient to the color specified in the **FillForegnd** cell.</span></span> 
  
 `THEMECBV(RGB(255,0,0), 2)`
  
<span data-ttu-id="f97b1-133">通过将第二个梯度停止点应用于红色的基色, 返回红色的底纹或淡色。</span><span class="sxs-lookup"><span data-stu-id="f97b1-133">Returns a shade or tint of red created by applying the second gradient stop to a base color of red.</span></span>
  

