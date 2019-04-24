---
title: Size 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251252
localization_priority: Normal
ms.assetid: a61b50fe-eacb-b3d4-0e4e-ab3e7c972ee9
description: 确定形状的文本块中文本的大小。
ms.openlocfilehash: ea747620301a07cafaf179106b54510edb95f7ed
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314796"
---
# <a name="size-cell-character-section"></a><span data-ttu-id="d183e-103">Size 单元格（“Character”内容）</span><span class="sxs-lookup"><span data-stu-id="d183e-103">Size Cell (Character Section)</span></span>

<span data-ttu-id="d183e-104">确定形状的文本块中文本的大小。</span><span class="sxs-lookup"><span data-stu-id="d183e-104">Determines the size of the text in the shape's text block.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d183e-105">注解</span><span class="sxs-lookup"><span data-stu-id="d183e-105">Remarks</span></span>

<span data-ttu-id="d183e-p101">文本大小与绘图比例无关。即使绘图比例进行调整，文本大小仍然保持不变。</span><span class="sxs-lookup"><span data-stu-id="d183e-p101">The text's size is independent of the scale of the drawing. If the drawing is scaled, the text size remains the same.</span></span>
  
<span data-ttu-id="d183e-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Size 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="d183e-108">To get a reference to the Size cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d183e-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="d183e-109">Cell name:</span></span>  <br/> | <span data-ttu-id="d183e-110">Char. Size [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="d183e-110">Char.Size[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="d183e-111">要从某个程序按索引获取对 Size 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="d183e-111">To get a reference to the Size cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="d183e-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="d183e-112">Section index:</span></span>  <br/> |<span data-ttu-id="d183e-113">**visSectionCharacter**</span><span class="sxs-lookup"><span data-stu-id="d183e-113">**visSectionCharacter**</span></span> <br/> |
| <span data-ttu-id="d183e-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="d183e-114">Row index:</span></span>  <br/> |<span data-ttu-id="d183e-115">**visRowCharacter** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="d183e-115">**visRowCharacter** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="d183e-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="d183e-116">Cell index:</span></span>  <br/> |<span data-ttu-id="d183e-117">**visCharacterSize**</span><span class="sxs-lookup"><span data-stu-id="d183e-117">**visCharacterSize**</span></span> <br/> |
   

