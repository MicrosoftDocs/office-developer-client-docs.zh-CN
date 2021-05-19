---
title: ISTHEMED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 91cde601-dca9-4737-afe1-bdf76638dfe3
description: 返回一个 Boolean 值，该值指示形状是否应用了主题。
ms.openlocfilehash: 49f53eaaacbdc86a633703d6ef847e38097f5122
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418118"
---
# <a name="isthemed-function"></a><span data-ttu-id="37d28-103">ISTHEMED 函数</span><span class="sxs-lookup"><span data-stu-id="37d28-103">ISTHEMED Function</span></span>

<span data-ttu-id="37d28-104">返回一个 Boolean 值，该值指示形状是否应用了主题。</span><span class="sxs-lookup"><span data-stu-id="37d28-104">Returns a Boolean value indicating whether a shape has a theme applied to it.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="37d28-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="37d28-105">Version Information</span></span>

<span data-ttu-id="37d28-106">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="37d28-106">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="37d28-107">语法</span><span class="sxs-lookup"><span data-stu-id="37d28-107">Syntax</span></span>

 <span data-ttu-id="37d28-108">**ISTHEMED** () </span><span class="sxs-lookup"><span data-stu-id="37d28-108">**ISTHEMED**()</span></span>
  
## <a name="return-value"></a><span data-ttu-id="37d28-109">返回值</span><span class="sxs-lookup"><span data-stu-id="37d28-109">Return value</span></span>

<span data-ttu-id="37d28-110">布尔值</span><span class="sxs-lookup"><span data-stu-id="37d28-110">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="37d28-111">备注</span><span class="sxs-lookup"><span data-stu-id="37d28-111">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="37d28-112">2013 中的 **ISTHEMED** Visio替换以前版本的 **CELLISTHEMED** 函数Visio。</span><span class="sxs-lookup"><span data-stu-id="37d28-112">The **ISTHEMED** function in Visio 2013 replaces the **CELLISTHEMED** function from previous versions of Visio.</span></span> 
  
<span data-ttu-id="37d28-113">**ISTHEMED** 函数允许您为形状分配主题格式的适当部分，但保留使用手动应用的格式覆盖主题格式的其他部分的功能。</span><span class="sxs-lookup"><span data-stu-id="37d28-113">The **ISTHEMED** function lets you assign appropriate parts of a theme's formatting to a shape but retain the ability to override other parts of the theme formatting with manually-applied formatting.</span></span> <span data-ttu-id="37d28-114">如果随后重新应用该主题，则任何手动格式都将被覆盖，并且形状将采用所有主题的格式。</span><span class="sxs-lookup"><span data-stu-id="37d28-114">If you subsequently reapply the theme, any manual formatting is overridden and the shape takes on all of the theme's formatting.</span></span> 
  
 <span data-ttu-id="37d28-115">如果形状中的 [ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md)单元格大于 0，**则 ISTHEMED** 计算结果为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="37d28-115">**ISTHEMED** evaluates to TRUE if the [ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md) cell in the shape is greater than 0.</span></span> <span data-ttu-id="37d28-116">如果此单元格等于 0，则 **ISTHEMED** 计算结果为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="37d28-116">If this cell is equal to 0, then **ISTHEMED** evaluates to FALSE.</span></span> <span data-ttu-id="37d28-117">DocumentSheet 和 PageSheet 的主题不会影响 ShapeSheet 中使用的 **ISTHEMED** 函数的值。</span><span class="sxs-lookup"><span data-stu-id="37d28-117">The theme of the DocumentSheet and PageSheet won't affect the value of the **ISTHEMED** function used in a ShapeSheet.</span></span> <span data-ttu-id="37d28-118">只有在 PageSheet 中显示 **ISTHEMED** 函数时，页面的主题才重要。</span><span class="sxs-lookup"><span data-stu-id="37d28-118">Only if the **ISTHEMED** function shows up in the PageSheet does the page's theme matter.</span></span> 
  
## <a name="example"></a><span data-ttu-id="37d28-119">示例</span><span class="sxs-lookup"><span data-stu-id="37d28-119">Example</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="37d28-120">Cell</span><span class="sxs-lookup"><span data-stu-id="37d28-120">Cell</span></span>  <br/> |<span data-ttu-id="37d28-121">公式</span><span class="sxs-lookup"><span data-stu-id="37d28-121">Formula</span></span>  <br/> |<span data-ttu-id="37d28-122">结果</span><span class="sxs-lookup"><span data-stu-id="37d28-122">Result</span></span>  <br/> |
|<span data-ttu-id="37d28-123">Char.Font</span><span class="sxs-lookup"><span data-stu-id="37d28-123">Char.Font</span></span>  <br/> |<span data-ttu-id="37d28-124">如果 (ISTHEMED () 、THEMEVAL () 、FONT ("Calibri") ) </span><span class="sxs-lookup"><span data-stu-id="37d28-124">IF(ISTHEMED(), THEMEVAL(), FONT("Calibri"))</span></span>  <br/> |<span data-ttu-id="37d28-125">如果形状应用了主题，则形状文本将接受主题中的字体格式。</span><span class="sxs-lookup"><span data-stu-id="37d28-125">If the shape has a themed applied to it, the shape text accepts the font formatting from the theme.</span></span> <span data-ttu-id="37d28-126">如果形状未设置其颜色，则形状文本的格式为"Calibri"字体。</span><span class="sxs-lookup"><span data-stu-id="37d28-126">If the shape is not themed, the shape text is formatted with the "Calibri" font.</span></span>  <br/> |
|<span data-ttu-id="37d28-127">LineColor</span><span class="sxs-lookup"><span data-stu-id="37d28-127">LineColor</span></span>  <br/> |<span data-ttu-id="37d28-128">如果 (ISTHEMED、RGB (255、0、0) 、RGB (0、255、0) ) </span><span class="sxs-lookup"><span data-stu-id="37d28-128">IF(ISTHEMED, RGB(255, 0, 0), RGB(0, 255, 0))</span></span>  <br/> |<span data-ttu-id="37d28-129">如果形状应用了一种颜色，则形状的线条颜色为红色。</span><span class="sxs-lookup"><span data-stu-id="37d28-129">If the shape has a themed applied to it, the shape's line color is red.</span></span> <span data-ttu-id="37d28-130">如果形状未设置其颜色，则形状的线条颜色为绿色。</span><span class="sxs-lookup"><span data-stu-id="37d28-130">If the shape is not themed, the shape's line color is green.</span></span>  <br/> |
   

