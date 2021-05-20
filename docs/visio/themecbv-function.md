---
title: THEMECBV 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ef62f63f-b2ce-4d12-a294-93dbdc9a869d
description: 返回一个 RGB 值或一个整数，它代表文档调色板中的索引，其中作为参数传入的颜色 (数字) 已由活动主题的渐变设置中存储的指定淡色或底纹值进行了修改。
ms.openlocfilehash: 014dc04c5114e296cd2226f3cf04dfb729817578
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429136"
---
# <a name="themecbv-function"></a><span data-ttu-id="5b1dc-103">THEMECBV 函数</span><span class="sxs-lookup"><span data-stu-id="5b1dc-103">THEMECBV Function</span></span>

<span data-ttu-id="5b1dc-104">返回一个 RGB 值或一个整数，它代表文档调色板中的索引，其中作为参数传入的颜色 (数字) 已由活动主题的渐变设置中存储的指定淡色或底纹值进行了修改。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-104">Returns an RGB value or an integer that represents an index in the document's color palette, where the color (number) passed in as an argument has been modified by the specified tint or shade value stored in the gradient settings of the active theme.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="5b1dc-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="5b1dc-105">Version Information</span></span>

<span data-ttu-id="5b1dc-106">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="5b1dc-106">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5b1dc-107">语法</span><span class="sxs-lookup"><span data-stu-id="5b1dc-107">Syntax</span></span>

 <span data-ttu-id="5b1dc-108">**THEMECBV** ( _color_，  _gradient_stop_number_) </span><span class="sxs-lookup"><span data-stu-id="5b1dc-108">**THEMECBV**( _color_,  _gradient_stop_number_)</span></span>
  
### <a name="parameters"></a><span data-ttu-id="5b1dc-109">参数</span><span class="sxs-lookup"><span data-stu-id="5b1dc-109">Parameters</span></span>

|<span data-ttu-id="5b1dc-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-110">**Name**</span></span>|<span data-ttu-id="5b1dc-111">**必需/可选**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-111">**Required/Optional**</span></span>|<span data-ttu-id="5b1dc-112">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-112">**Data Type**</span></span>|<span data-ttu-id="5b1dc-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5b1dc-114">_color_</span><span class="sxs-lookup"><span data-stu-id="5b1dc-114">_color_</span></span> <br/> |<span data-ttu-id="5b1dc-115">必需</span><span class="sxs-lookup"><span data-stu-id="5b1dc-115">Required</span></span>  <br/> |<span data-ttu-id="5b1dc-116">**Number**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-116">**Number**</span></span> <br/> |<span data-ttu-id="5b1dc-117">一个数字，代表文档的调色板中的索引。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-117">A number representing an index in the document's color palette.</span></span>  <br/> |
| <span data-ttu-id="5b1dc-118">_gradient_stop_number_</span><span class="sxs-lookup"><span data-stu-id="5b1dc-118">_gradient_stop_number_</span></span> <br/> |<span data-ttu-id="5b1dc-119">必需</span><span class="sxs-lookup"><span data-stu-id="5b1dc-119">Required</span></span>  <br/> |<span data-ttu-id="5b1dc-120">**Number**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-120">**Number**</span></span> <br/> |<span data-ttu-id="5b1dc-121">渐变停止 (淡色) 存储在要应用于颜色的活动主题的渐变设置中。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-121">The gradient stop (tint or shade) stored in the gradient settings of the active theme to apply to the color.</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="5b1dc-122">返回值</span><span class="sxs-lookup"><span data-stu-id="5b1dc-122">Return value</span></span>

 <span data-ttu-id="5b1dc-123">**Number**</span><span class="sxs-lookup"><span data-stu-id="5b1dc-123">**Number**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5b1dc-124">备注</span><span class="sxs-lookup"><span data-stu-id="5b1dc-124">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="5b1dc-125">如果分配给形状的 QuickStyle 没有渐变，则 THEMECBV 函数对作为参数传入的颜色不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-125">The THEMECBV function does nothing to the color passed in as an argument if the QuickStyle that is assigned to the shape does not have a gradient.</span></span> 
  
<span data-ttu-id="5b1dc-126">主题中的渐变设置是一系列编号的渐变停点，对应于"变亮" (淡色) 或"变暗" (阴影) 。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-126">The gradient settings in a theme are a series of numbered gradient stops that correspond to a "lightening" (tint) or "darkening" (shade).</span></span> <span data-ttu-id="5b1dc-127">这些底纹和淡色应用于基本颜色以创建渐变颜色效果。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-127">These shades and tints are applied to a base color to create a gradient color effect.</span></span>
  
<span data-ttu-id="5b1dc-128">**THEMECBV** 函数采用颜色输入，在颜色被指定渐变停点淡色或底纹修改后输出颜色。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-128">The **THEMECBV** function takes a color input and outputs the color after it has been modified by the tint or shade of the specified gradient stop.</span></span> <span data-ttu-id="5b1dc-129">如果当前快速样式包含渐变填充，则淡色和底纹来自主题的定义。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-129">The tints and shades come from the theme's definition, if the current quick style contains a gradient fill.</span></span> <span data-ttu-id="5b1dc-130">如果活动"快速样式"未指定渐变填充或形状设置为"无主题"，则此公式只返回为第一个参数传入的颜色。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-130">If the active Quick Style does not specify a gradient fill or the shape is set to No Theme, then this formula simply returns the color that was passed in for the first argument.</span></span> 
  
## <a name="example"></a><span data-ttu-id="5b1dc-131">示例</span><span class="sxs-lookup"><span data-stu-id="5b1dc-131">Example</span></span>

 `THEMECBV(FillForegnd, 5)`
  
<span data-ttu-id="5b1dc-132">返回通过将渐变的第五个渐变停止点中的淡色或底纹应用于 **FillForegnd** 单元格中指定的颜色而创建的颜色。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-132">Returns the color created by applying the tint or shade in the fifth gradient stop of the gradient to the color specified in the **FillForegnd** cell.</span></span> 
  
 `THEMECBV(RGB(255,0,0), 2)`
  
<span data-ttu-id="5b1dc-133">返回通过将第二个渐变停止点应用于红色基色而创建的红色底纹或淡色。</span><span class="sxs-lookup"><span data-stu-id="5b1dc-133">Returns a shade or tint of red created by applying the second gradient stop to a base color of red.</span></span>
  

