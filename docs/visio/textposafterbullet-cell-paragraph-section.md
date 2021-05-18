---
title: TextPosAfterBullet 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60089
localization_priority: Normal
ms.assetid: 08958abb-9d66-5a83-dac3-4cbfd1f6d85e
description: 表示段落的第一行和项目符号之间的距离。
ms.openlocfilehash: a98967cb5f9541434745c3b3d6afafde0878074a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422150"
---
# <a name="textposafterbullet-cell-paragraph-section"></a><span data-ttu-id="c3a02-103">TextPosAfterBullet 单元格（“Paragraph”内容）</span><span class="sxs-lookup"><span data-stu-id="c3a02-103">TextPosAfterBullet Cell (Paragraph Section)</span></span>

<span data-ttu-id="c3a02-104">表示段落的第一行和项目符号之间的距离。</span><span class="sxs-lookup"><span data-stu-id="c3a02-104">Represents the distance between the first line of the paragraph and the bullet.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c3a02-105">备注</span><span class="sxs-lookup"><span data-stu-id="c3a02-105">Remarks</span></span>

<span data-ttu-id="c3a02-p101">此距离将与 IndFirst 单元格中包含的距离（默认的左缩近）相加。此值与绘图比例无关。</span><span class="sxs-lookup"><span data-stu-id="c3a02-p101">This distance is added to the distance contained in the IndFirst cell, which is the default left indent. This value is independent of the scale of the drawing.</span></span> 
  
<span data-ttu-id="c3a02-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TextPosAfterBullet 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="c3a02-108">To get a reference to the TextPosAfterBullet cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c3a02-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="c3a02-109">Cell name:</span></span>  <br/> | <span data-ttu-id="c3a02-110">Para.TextPosAfterBullet[  *i*  ] 其中  *i*  = <1>， 2， 3...</span><span class="sxs-lookup"><span data-stu-id="c3a02-110">Para.TextPosAfterBullet[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="c3a02-111">要从某个程序按索引获取对 TextPosAfterBullet 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="c3a02-111">To get a reference to the TextPosAfterBullet cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="c3a02-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="c3a02-112">Section index:</span></span>  <br/> |<span data-ttu-id="c3a02-113">**visSectionParagraph**</span><span class="sxs-lookup"><span data-stu-id="c3a02-113">**visSectionParagraph**</span></span> <br/> |
| <span data-ttu-id="c3a02-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="c3a02-114">Row index:</span></span>  <br/> |<span data-ttu-id="c3a02-115">**visRowParagraph**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="c3a02-115">**visRowParagraph** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="c3a02-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="c3a02-116">Cell index:</span></span>  <br/> |<span data-ttu-id="c3a02-117">**visTextPosAfterBullet**</span><span class="sxs-lookup"><span data-stu-id="c3a02-117">**visTextPosAfterBullet**</span></span> <br/> |
   

