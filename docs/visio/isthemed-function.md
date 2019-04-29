---
title: ISTHEMED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 91cde601-dca9-4737-afe1-bdf76638dfe3
description: 返回一个布尔值, 该值指示是否对形状应用了主题。
ms.openlocfilehash: 49f53eaaacbdc86a633703d6ef847e38097f5122
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418118"
---
# <a name="isthemed-function"></a><span data-ttu-id="d2337-103">ISTHEMED 函数</span><span class="sxs-lookup"><span data-stu-id="d2337-103">ISTHEMED Function</span></span>

<span data-ttu-id="d2337-104">返回一个布尔值, 该值指示是否对形状应用了主题。</span><span class="sxs-lookup"><span data-stu-id="d2337-104">Returns a Boolean value indicating whether a shape has a theme applied to it.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="d2337-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="d2337-105">Version Information</span></span>

<span data-ttu-id="d2337-106">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="d2337-106">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="d2337-107">语法</span><span class="sxs-lookup"><span data-stu-id="d2337-107">Syntax</span></span>

 <span data-ttu-id="d2337-108">**ISTHEMED**()</span><span class="sxs-lookup"><span data-stu-id="d2337-108">**ISTHEMED**()</span></span>
  
## <a name="return-value"></a><span data-ttu-id="d2337-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d2337-109">Return value</span></span>

<span data-ttu-id="d2337-110">布尔值</span><span class="sxs-lookup"><span data-stu-id="d2337-110">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d2337-111">备注</span><span class="sxs-lookup"><span data-stu-id="d2337-111">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="d2337-112">visio 2013 中的**ISTHEMED**函数将替换以前版本的 visio 中的**CELLISTHEMED**函数。</span><span class="sxs-lookup"><span data-stu-id="d2337-112">The **ISTHEMED** function in Visio 2013 replaces the **CELLISTHEMED** function from previous versions of Visio.</span></span> 
  
<span data-ttu-id="d2337-113">**ISTHEMED**函数允许您将主题格式的相应部分分配给形状, 但仍可以使用手动应用的格式替代主题格式设置的其他部分。</span><span class="sxs-lookup"><span data-stu-id="d2337-113">The **ISTHEMED** function lets you assign appropriate parts of a theme's formatting to a shape but retain the ability to override other parts of the theme formatting with manually-applied formatting.</span></span> <span data-ttu-id="d2337-114">如果您随后重新应用主题, 则任何手动的格式都将被覆盖, 并且形状将采用主题的所有格式。</span><span class="sxs-lookup"><span data-stu-id="d2337-114">If you subsequently reapply the theme, any manual formatting is overridden and the shape takes on all of the theme's formatting.</span></span> 
  
 <span data-ttu-id="d2337-115">如果形状中的[ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md)单元格大于 0, 则**ISTHEMED**的计算结果为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d2337-115">**ISTHEMED** evaluates to TRUE if the [ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md) cell in the shape is greater than 0.</span></span> <span data-ttu-id="d2337-116">如果此单元格等于 0, 则**ISTHEMED**的计算结果为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d2337-116">If this cell is equal to 0, then **ISTHEMED** evaluates to FALSE.</span></span> <span data-ttu-id="d2337-117">DocumentSheet 和 PageSheet 的主题不会影响 ShapeSheet 中使用的**ISTHEMED**函数的值。</span><span class="sxs-lookup"><span data-stu-id="d2337-117">The theme of the DocumentSheet and PageSheet won't affect the value of the **ISTHEMED** function used in a ShapeSheet.</span></span> <span data-ttu-id="d2337-118">仅当**ISTHEMED**函数在 PageSheet 中显示时, 才会执行页面的主题事务。</span><span class="sxs-lookup"><span data-stu-id="d2337-118">Only if the **ISTHEMED** function shows up in the PageSheet does the page's theme matter.</span></span> 
  
## <a name="example"></a><span data-ttu-id="d2337-119">示例</span><span class="sxs-lookup"><span data-stu-id="d2337-119">Example</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="d2337-120">Cell</span><span class="sxs-lookup"><span data-stu-id="d2337-120">Cell</span></span>  <br/> |<span data-ttu-id="d2337-121">公式</span><span class="sxs-lookup"><span data-stu-id="d2337-121">Formula</span></span>  <br/> |<span data-ttu-id="d2337-122">结果</span><span class="sxs-lookup"><span data-stu-id="d2337-122">Result</span></span>  <br/> |
|<span data-ttu-id="d2337-123">字符。字体</span><span class="sxs-lookup"><span data-stu-id="d2337-123">Char.Font</span></span>  <br/> |<span data-ttu-id="d2337-124">IF (ISTHEMED ()、THEMEVAL () 和 FONT ("Calibri"))</span><span class="sxs-lookup"><span data-stu-id="d2337-124">IF(ISTHEMED(), THEMEVAL(), FONT("Calibri"))</span></span>  <br/> |<span data-ttu-id="d2337-125">如果形状应用了主题, 则形状文本接受主题中的字体格式。</span><span class="sxs-lookup"><span data-stu-id="d2337-125">If the shape has a themed applied to it, the shape text accepts the font formatting from the theme.</span></span> <span data-ttu-id="d2337-126">如果形状没有主题, 则形状文本的格式为 "Calibri" 字体。</span><span class="sxs-lookup"><span data-stu-id="d2337-126">If the shape is not themed, the shape text is formatted with the "Calibri" font.</span></span>  <br/> |
|<span data-ttu-id="d2337-127">LineColor</span><span class="sxs-lookup"><span data-stu-id="d2337-127">LineColor</span></span>  <br/> |<span data-ttu-id="d2337-128">IF (ISTHEMED, rgb (255, 0, 0), RGB (0, 255, 0))</span><span class="sxs-lookup"><span data-stu-id="d2337-128">IF(ISTHEMED, RGB(255, 0, 0), RGB(0, 255, 0))</span></span>  <br/> |<span data-ttu-id="d2337-129">如果形状应用了主题, 则该形状的线条颜色为红色。</span><span class="sxs-lookup"><span data-stu-id="d2337-129">If the shape has a themed applied to it, the shape's line color is red.</span></span> <span data-ttu-id="d2337-130">如果形状没有主题, 则形状的线条颜色为绿色。</span><span class="sxs-lookup"><span data-stu-id="d2337-130">If the shape is not themed, the shape's line color is green.</span></span>  <br/> |
   

