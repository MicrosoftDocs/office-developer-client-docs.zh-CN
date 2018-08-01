---
title: ISTHEMED 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 91cde601-dca9-4737-afe1-bdf76638dfe3
description: 返回一个 Boolean 值，该值形状是否含有向其应用了主题。
ms.openlocfilehash: 4311780d8686b5792e999c204ec182d23efb723c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780515"
---
# <a name="isthemed-function"></a><span data-ttu-id="b8563-103">ISTHEMED 函数</span><span class="sxs-lookup"><span data-stu-id="b8563-103">ISTHEMED Function</span></span>

<span data-ttu-id="b8563-104">返回一个 Boolean 值，该值形状是否含有向其应用了主题。</span><span class="sxs-lookup"><span data-stu-id="b8563-104">Returns a Boolean value indicating whether a shape has a theme applied to it.</span></span> 
  
## <a name="version-information"></a><span data-ttu-id="b8563-105">版本信息</span><span class="sxs-lookup"><span data-stu-id="b8563-105">Version Information</span></span>

<span data-ttu-id="b8563-106">添加的版本： Visio 2013
</span><span class="sxs-lookup"><span data-stu-id="b8563-106">Version Added: Visio 2013</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b8563-107">语法</span><span class="sxs-lookup"><span data-stu-id="b8563-107">Syntax</span></span>

 <span data-ttu-id="b8563-108">**ISTHEMED**()</span><span class="sxs-lookup"><span data-stu-id="b8563-108">**ISTHEMED**()</span></span>
  
## <a name="return-value"></a><span data-ttu-id="b8563-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b8563-109">Return value</span></span>

<span data-ttu-id="b8563-110">Boolean</span><span class="sxs-lookup"><span data-stu-id="b8563-110">Boolean</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b8563-111">说明</span><span class="sxs-lookup"><span data-stu-id="b8563-111">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="b8563-112">Visio 2013 中的**ISTHEMED**函数替换为从早期版本的 Visio **CELLISTHEMED**函数。</span><span class="sxs-lookup"><span data-stu-id="b8563-112">The **ISTHEMED** function in Visio 2013 replaces the **CELLISTHEMED** function from previous versions of Visio.</span></span> 
  
<span data-ttu-id="b8563-113">**ISTHEMED**函数，可以向形状分配相应部分的主题格式，但保留重写该主题的格式与手动应用格式的其他部分的能力。</span><span class="sxs-lookup"><span data-stu-id="b8563-113">The **ISTHEMED** function lets you assign appropriate parts of a theme's formatting to a shape but retain the ability to override other parts of the theme formatting with manually-applied formatting.</span></span> <span data-ttu-id="b8563-114">如果您随后重新应用主题，任何手动格式将被覆盖并形状承担的所有主题的格式。</span><span class="sxs-lookup"><span data-stu-id="b8563-114">If you subsequently reapply the theme, any manual formatting is overridden and the shape takes on all of the theme's formatting.</span></span> 
  
 <span data-ttu-id="b8563-115">**ISTHEMED**计算结果为形状中的[ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md)单元格为大于 0 时为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="b8563-115">**ISTHEMED** evaluates to TRUE if the [ColorSchemeIndex](colorschemeindex-cell-theme-properties-section.md) cell in the shape is greater than 0.</span></span> <span data-ttu-id="b8563-116">如果此单元格等于 0，然后**ISTHEMED**计算结果为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b8563-116">If this cell is equal to 0, then **ISTHEMED** evaluates to FALSE.</span></span> <span data-ttu-id="b8563-117">主题的 DocumentSheet 和 PageSheet 不会影响在 ShapeSheet 中使用**ISTHEMED**函数的值。</span><span class="sxs-lookup"><span data-stu-id="b8563-117">The theme of the DocumentSheet and PageSheet won't affect the value of the **ISTHEMED** function used in a ShapeSheet.</span></span> <span data-ttu-id="b8563-118">仅当**ISTHEMED**函数中显示 PageSheet 执行的页面的主题专家。</span><span class="sxs-lookup"><span data-stu-id="b8563-118">Only if the **ISTHEMED** function shows up in the PageSheet does the page's theme matter.</span></span> 
  
## <a name="example"></a><span data-ttu-id="b8563-119">示例</span><span class="sxs-lookup"><span data-stu-id="b8563-119">Example</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="b8563-120">单元格</span><span class="sxs-lookup"><span data-stu-id="b8563-120">Cell</span></span>  <br/> |<span data-ttu-id="b8563-121">公式</span><span class="sxs-lookup"><span data-stu-id="b8563-121">Formula</span></span>  <br/> |<span data-ttu-id="b8563-122">结果</span><span class="sxs-lookup"><span data-stu-id="b8563-122">Result</span></span>  <br/> |
|<span data-ttu-id="b8563-123">Char.Font</span><span class="sxs-lookup"><span data-stu-id="b8563-123">Char.Font</span></span>  <br/> |<span data-ttu-id="b8563-124">IF(ISTHEMED()，THEMEVAL()，FONT("Calibri"))</span><span class="sxs-lookup"><span data-stu-id="b8563-124">IF(ISTHEMED(), THEMEVAL(), FONT("Calibri"))</span></span>  <br/> |<span data-ttu-id="b8563-125">如果应用了主题应用于该形状，形状文本接受的字体格式设置的主题。</span><span class="sxs-lookup"><span data-stu-id="b8563-125">If the shape has a themed applied to it, the shape text accepts the font formatting from the theme.</span></span> <span data-ttu-id="b8563-126">如果形状不是应用了主题，"宋体"字体格式形状文本。</span><span class="sxs-lookup"><span data-stu-id="b8563-126">If the shape is not themed, the shape text is formatted with the "Calibri" font.</span></span>  <br/> |
|<span data-ttu-id="b8563-127">LineColor</span><span class="sxs-lookup"><span data-stu-id="b8563-127">LineColor</span></span>  <br/> |<span data-ttu-id="b8563-128">如果 (ISTHEMED，RGB （255，0，0）、 RGB （0、 255，0）)</span><span class="sxs-lookup"><span data-stu-id="b8563-128">IF(ISTHEMED, RGB(255, 0, 0), RGB(0, 255, 0))</span></span>  <br/> |<span data-ttu-id="b8563-129">如果应用了主题应用于该形状，该形状的线条颜色为红色。</span><span class="sxs-lookup"><span data-stu-id="b8563-129">If the shape has a themed applied to it, the shape's line color is red.</span></span> <span data-ttu-id="b8563-130">如果形状不是应用了主题的该形状的线条颜色为绿色。</span><span class="sxs-lookup"><span data-stu-id="b8563-130">If the shape is not themed, the shape's line color is green.</span></span>  <br/> |
   

