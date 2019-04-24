---
title: Style 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251249
localization_priority: Normal
ms.assetid: 4372f1e1-f0a9-2f63-ff79-58f2afdceed5
description: 显示应用于形状的文本块中一定范围内的文本的字符格式。
ms.openlocfilehash: 349bdc42485aa511011aeb85a43f1ab3e4ea853d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329809"
---
# <a name="style-cell-character-section"></a><span data-ttu-id="21723-103">Style 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="21723-103">Style Cell (Character Section)</span></span>

<span data-ttu-id="21723-104">显示应用于形状的文本块中一定范围内的文本的字符格式。</span><span class="sxs-lookup"><span data-stu-id="21723-104">Shows the character formatting applied to a range of text in the shape's text block.</span></span>
  
|<span data-ttu-id="21723-105">**Style**</span><span class="sxs-lookup"><span data-stu-id="21723-105">**Style**</span></span>|<span data-ttu-id="21723-106">**值**</span><span class="sxs-lookup"><span data-stu-id="21723-106">**Value**</span></span>|<span data-ttu-id="21723-107">**自动常量**</span><span class="sxs-lookup"><span data-stu-id="21723-107">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="21723-108">粗体</span><span class="sxs-lookup"><span data-stu-id="21723-108">Bold</span></span>  <br/> | <span data-ttu-id="21723-109">&amp;H1</span><span class="sxs-lookup"><span data-stu-id="21723-109">&amp;H1</span></span>  <br/> |<span data-ttu-id="21723-110">**visBold**</span><span class="sxs-lookup"><span data-stu-id="21723-110">**visBold**</span></span> <br/> |
| <span data-ttu-id="21723-111">斜体</span><span class="sxs-lookup"><span data-stu-id="21723-111">Italic</span></span>  <br/> | <span data-ttu-id="21723-112">&amp;H2</span><span class="sxs-lookup"><span data-stu-id="21723-112">&amp;H2</span></span>  <br/> |<span data-ttu-id="21723-113">**visItalic**</span><span class="sxs-lookup"><span data-stu-id="21723-113">**visItalic**</span></span> <br/> |
| <span data-ttu-id="21723-114">下划线</span><span class="sxs-lookup"><span data-stu-id="21723-114">Underline</span></span>  <br/> | <span data-ttu-id="21723-115">&amp;H4</span><span class="sxs-lookup"><span data-stu-id="21723-115">&amp;H4</span></span>  <br/> |<span data-ttu-id="21723-116">**visUnderLine**</span><span class="sxs-lookup"><span data-stu-id="21723-116">**visUnderLine**</span></span> <br/> |
| <span data-ttu-id="21723-117">小型大写字母</span><span class="sxs-lookup"><span data-stu-id="21723-117">Small caps</span></span>  <br/> | <span data-ttu-id="21723-118">&amp;H8</span><span class="sxs-lookup"><span data-stu-id="21723-118">&amp;H8</span></span>  <br/> |<span data-ttu-id="21723-119">**visSmallCaps**</span><span class="sxs-lookup"><span data-stu-id="21723-119">**visSmallCaps**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="21723-120">注解</span><span class="sxs-lookup"><span data-stu-id="21723-120">Remarks</span></span>

<span data-ttu-id="21723-p101">如果“Character”内容包含多行，则 Style 单元格包含应用于某形状文本的一个子范围的格式编排信息。否则，它就包含该形状的所有文本的格式设置信息。</span><span class="sxs-lookup"><span data-stu-id="21723-p101">The Style cell contains formatting information applied to a sub-range of a shape's text if the Characters section contains multiple rows. Otherwise, it contains formatting information for all of the shape's text.</span></span>
  
<span data-ttu-id="21723-123">该值表示二进制数字，其中每位代表均一种字符样式。</span><span class="sxs-lookup"><span data-stu-id="21723-123">The value represents a binary number in which each bit indicates a character style.</span></span> <span data-ttu-id="21723-124">例如，值 3 表示格式既是斜体又是粗体的文本。</span><span class="sxs-lookup"><span data-stu-id="21723-124">For example, a value of 3 represents text formatted in both italic and bold.</span></span> <span data-ttu-id="21723-125">如果样式值为 0，则该文本是纯文本，即未设定任何格式。</span><span class="sxs-lookup"><span data-stu-id="21723-125">If the value of Style is 0, the text is plain, or unformatted.</span></span> <span data-ttu-id="21723-126">您可以使用布尔位\*函数测试特定的格式。</span><span class="sxs-lookup"><span data-stu-id="21723-126">You can test for a particular format using Boolean BIT\* functions.</span></span> <span data-ttu-id="21723-127">有关这些函数的详细信息，请参考编程文档。</span><span class="sxs-lookup"><span data-stu-id="21723-127">See your programming documentation for details about these functions.</span></span>
  
<span data-ttu-id="21723-128">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Style 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="21723-128">To get a reference to the Style cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="21723-129">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="21723-129">Cell name:</span></span>  <br/> | <span data-ttu-id="21723-130">Char. 样式 [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="21723-130">Char.Style[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="21723-131">要从某个程序按索引获取对 Style 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="21723-131">To get a reference to the Style cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="21723-132">内容索引：</span><span class="sxs-lookup"><span data-stu-id="21723-132">Section index:</span></span>  <br/> |<span data-ttu-id="21723-133">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="21723-133">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="21723-134">行索引：</span><span class="sxs-lookup"><span data-stu-id="21723-134">Row index:</span></span>  <br/> |<span data-ttu-id="21723-135">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="21723-135">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="21723-136">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="21723-136">Cell index:</span></span>  <br/> |<span data-ttu-id="21723-137">**visCharacterStyle**</span><span class="sxs-lookup"><span data-stu-id="21723-137">**visCharacterStyle**</span></span> <br/> |
   
 <span data-ttu-id="21723-138">*示例*</span><span class="sxs-lookup"><span data-stu-id="21723-138">*Example*</span></span> 
  
<span data-ttu-id="21723-139">假设在某形状的“Character”内容的第一行中，Color 单元格设置为以下公式：</span><span class="sxs-lookup"><span data-stu-id="21723-139">Suppose the Color cell in the first row of a shape's Character section is set to this formula:</span></span>
  
<span data-ttu-id="21723-140">= IF (BITAND (Char. Style, 1) = 1, 4, 3)</span><span class="sxs-lookup"><span data-stu-id="21723-140">= IF(BITAND(Char.Style,1)=1,4,3)</span></span>
  
<span data-ttu-id="21723-p103">那么，如果形状的文本的第一个字符是粗体，则第一个“Character”属性行所涵盖的文本将是蓝色 (4)；否则，它将是绿色 (3)。此示例假设默认颜色有效。</span><span class="sxs-lookup"><span data-stu-id="21723-p103">Then if the first character of the shape's text is bold, the text covered by the first Character properties row will be blue (4); otherwise it will be green (3). This example assumes default colors are in effect.</span></span>
  
<span data-ttu-id="21723-p104">下面是一个在程序中设置 Style 单元格的例子。第一条语句按名称引用 Style 单元格，第二条语句按索引引用 Style 单元格。两条语句都在由形状的“Character”内容的第二行所涵盖的文本中应用斜体。</span><span class="sxs-lookup"><span data-stu-id="21723-p104">The following is an example of setting the Style cell in a program. The first statement references the Style cell by name, and the second statement references the Style cell by index. Both statements apply italic to the text covered by the second row of a shape's Character section.</span></span>
  

