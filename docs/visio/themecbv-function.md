---
title: THEMECBV 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ef62f63f-b2ce-4d12-a294-93dbdc9a869d
description: 返回 RGB 值或一个整数，表示在文档的调色板中的索引中的活动主题的渐变设置存储的指定淡色或底纹值其中已修改作为参数传入的颜色 （数目）。
ms.openlocfilehash: 878da505a840234445d3e16d3b8a68e31eaf5fda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781518"
---
# <a name="themecbv-function"></a><span data-ttu-id="1eb3f-103">THEMECBV 函数</span><span class="sxs-lookup"><span data-stu-id="1eb3f-103">THEMECBV Function</span></span>

<span data-ttu-id="1eb3f-104">返回 RGB 值或一个整数，表示在文档的调色板中的索引中的活动主题的渐变设置存储的指定淡色或底纹值其中已修改作为参数传入的颜色 （数目）。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-104">Returns an RGB value or an integer that represents an index in the document's color palette, where the color (number) passed in as an argument has been modified by the specified tint or shade value stored in the gradient settings of the active theme.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="1eb3f-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="1eb3f-105">Version Information</span></span>

<span data-ttu-id="1eb3f-106">添加的版本： Visio 2013</span><span class="sxs-lookup"><span data-stu-id="1eb3f-106">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1eb3f-107">语法</span><span class="sxs-lookup"><span data-stu-id="1eb3f-107">Syntax</span></span>

 <span data-ttu-id="1eb3f-108">**THEMECBV**（_颜色_， _gradient_stop_number_）</span><span class="sxs-lookup"><span data-stu-id="1eb3f-108">**THEMECBV**( _color_,  _gradient_stop_number_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="1eb3f-109">参数</span><span class="sxs-lookup"><span data-stu-id="1eb3f-109">Parameters</span></span>

|<span data-ttu-id="1eb3f-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-110">**Name**</span></span>|<span data-ttu-id="1eb3f-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-111">**Required/Optional**</span></span>|<span data-ttu-id="1eb3f-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-112">**Data Type**</span></span>|<span data-ttu-id="1eb3f-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1eb3f-114">_color_</span><span class="sxs-lookup"><span data-stu-id="1eb3f-114">_color_</span></span> <br/> |<span data-ttu-id="1eb3f-115">必需</span><span class="sxs-lookup"><span data-stu-id="1eb3f-115">Required</span></span>  <br/> |<span data-ttu-id="1eb3f-116">**编号**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-116">**Number**</span></span> <br/> |<span data-ttu-id="1eb3f-117">代表文档的调色板中的索引号。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-117">A number representing an index in the document's color palette.</span></span>  <br/> |
| <span data-ttu-id="1eb3f-118">_gradient_stop_number_</span><span class="sxs-lookup"><span data-stu-id="1eb3f-118">_gradient_stop_number_</span></span> <br/> |<span data-ttu-id="1eb3f-119">必需</span><span class="sxs-lookup"><span data-stu-id="1eb3f-119">Required</span></span>  <br/> |<span data-ttu-id="1eb3f-120">**编号**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-120">**Number**</span></span> <br/> |<span data-ttu-id="1eb3f-121">渐变光圈 （淡色或底纹） 存储中的活动主题的渐变设置要应用的颜色。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-121">The gradient stop (tint or shade) stored in the gradient settings of the active theme to apply to the color.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="1eb3f-122">返回值</span><span class="sxs-lookup"><span data-stu-id="1eb3f-122">Return value</span></span>

 <span data-ttu-id="1eb3f-123">**编号**</span><span class="sxs-lookup"><span data-stu-id="1eb3f-123">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1eb3f-124">备注</span><span class="sxs-lookup"><span data-stu-id="1eb3f-124">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="1eb3f-125">THEMECBV 函数无实际作用如果 QuickStyle 使用分配给该形状没有渐变作为参数传递中的颜色。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-125">The THEMECBV function does nothing to the color passed in as an argument if the QuickStyle that is assigned to the shape does not have a gradient.</span></span> 
  
<span data-ttu-id="1eb3f-126">主题中的渐变设置是一系列的编号对应于"浅色"（淡色） 或"变暗"（%底纹） 的渐变光圈。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-126">The gradient settings in a theme are a series of numbered gradient stops that correspond to a "lightening" (tint) or "darkening" (shade).</span></span> <span data-ttu-id="1eb3f-127">这些阴影和淡色于要创建的渐变颜色效果的基本颜色。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-127">These shades and tints are applied to a base color to create a gradient color effect.</span></span>
  
<span data-ttu-id="1eb3f-128">**THEMECBV**采用颜色输入和输出颜色后它已修改的色调或指定渐变光圈 %底纹。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-128">The **THEMECBV** function takes a color input and outputs the color after it has been modified by the tint or shade of the specified gradient stop.</span></span> <span data-ttu-id="1eb3f-129">淡色和阴影来自主题的定义，如果当前的快速样式包含渐变填充。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-129">The tints and shades come from the theme's definition, if the current quick style contains a gradient fill.</span></span> <span data-ttu-id="1eb3f-130">如果活动的快速样式没有指定渐变填充或形状设置为无主题，此公式将只返回第一个参数中传递的颜色。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-130">If the active Quick Style does not specify a gradient fill or the shape is set to No Theme, then this formula simply returns the color that was passed in for the first argument.</span></span> 
  
## <a name="example"></a><span data-ttu-id="1eb3f-131">示例</span><span class="sxs-lookup"><span data-stu-id="1eb3f-131">Example</span></span>

 `THEMECBV(FillForegnd, 5)`
  
<span data-ttu-id="1eb3f-132">返回由将淡色或中第五个渐变光圈的渐变底纹应用于指定在**FillForegnd**单元格的颜色的颜色。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-132">Returns the color created by applying the tint or shade in the fifth gradient stop of the gradient to the color specified in the **FillForegnd** cell.</span></span> 
  
 `THEMECBV(RGB(255,0,0), 2)`
  
<span data-ttu-id="1eb3f-133">返回底纹或创建的第二个渐变光圈应用到基本颜色的红色的红色的淡色。</span><span class="sxs-lookup"><span data-stu-id="1eb3f-133">Returns a shade or tint of red created by applying the second gradient stop to a base color of red.</span></span>
  

