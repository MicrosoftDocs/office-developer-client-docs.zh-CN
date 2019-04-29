---
title: BulletFont 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60023
localization_priority: Normal
ms.assetid: a75ff1f3-2f4d-89e3-108b-e16a34f5184f
description: 表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。
ms.openlocfilehash: 1cf04917bb7dfa68ee9395abb66ffe9e150f0273
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438461"
---
# <a name="bulletfont-cell-paragraph-section"></a><span data-ttu-id="e9ac6-103">BulletFont 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="e9ac6-103">BulletFont Cell (Paragraph Section)</span></span>

<span data-ttu-id="e9ac6-104">表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。</span><span class="sxs-lookup"><span data-stu-id="e9ac6-104">Represents the number of the font used to format the text when a custom bullet string is specified and the value in the Bullet cell is non-zero.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e9ac6-105">说明</span><span class="sxs-lookup"><span data-stu-id="e9ac6-105">Remarks</span></span>

<span data-ttu-id="e9ac6-p101">根据您的系统上安装的字体，字体编号会有所不同。如果该值是 0 并且有自定义项目符号字符串，则所使用的字体与该段落的第一个字符的字体相同。</span><span class="sxs-lookup"><span data-stu-id="e9ac6-p101">Font numbers vary according to the fonts installed on your system. If the value is 0 and there is a custom bullet string, the font used is the same as the font of the first character of the paragraph.</span></span>
  
<span data-ttu-id="e9ac6-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BulletFont 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="e9ac6-108">To get a reference to the BulletFont cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e9ac6-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="e9ac6-109">Cell name:</span></span>  <br/> | <span data-ttu-id="e9ac6-110">BulletFont [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="e9ac6-110">Para.BulletFont[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="e9ac6-111">要从某个程序按索引获取对 BulletFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="e9ac6-111">To get a reference to the BulletFont cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="e9ac6-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="e9ac6-112">Section index:</span></span>  <br/> |<span data-ttu-id="e9ac6-113">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="e9ac6-113">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="e9ac6-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="e9ac6-114">Row index:</span></span>  <br/> |<span data-ttu-id="e9ac6-115">**visRowParagraph** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="e9ac6-115">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="e9ac6-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="e9ac6-116">Cell index:</span></span>  <br/> |<span data-ttu-id="e9ac6-117">**visBulletFont**</span><span class="sxs-lookup"><span data-stu-id="e9ac6-117">**visBulletFont**</span></span> <br/> |
   

