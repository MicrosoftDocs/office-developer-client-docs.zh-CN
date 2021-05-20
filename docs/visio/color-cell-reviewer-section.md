---
title: Color 单元格（“Reviewer”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60032
localization_priority: Normal
ms.assetid: c1e3d7bf-e6b6-65f1-ae40-80c8ba4821cd
description: 一个 RGB 值，表示分配给文档审阅者的标记的颜色。
ms.openlocfilehash: d9df6605ca6c8a22353978b9483989ecfc08130d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430537"
---
# <a name="color-cell-reviewer-section"></a><span data-ttu-id="19418-103">Color 单元格（“Reviewer”内容）</span><span class="sxs-lookup"><span data-stu-id="19418-103">Color Cell (Reviewer Section)</span></span>

<span data-ttu-id="19418-104">一个 RGB 值，表示分配给文档审阅者的标记的颜色。</span><span class="sxs-lookup"><span data-stu-id="19418-104">An RGB value that represents the color assigned to a document reviewer's markup.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="19418-105">备注</span><span class="sxs-lookup"><span data-stu-id="19418-105">Remarks</span></span>

<span data-ttu-id="19418-p101">分配给审阅者的颜色顺序如下：红色、蓝色、绿色、紫色、橙色、青绿色、灰色。这些颜色循环分配给其余审阅者。</span><span class="sxs-lookup"><span data-stu-id="19418-p101">Colors are assigned to reviewers in the following sequence: red, blue, green, violet, orange, turquoise, gray. These colors are cycled through again for any remaining reviewers.</span></span> 
  
<span data-ttu-id="19418-108">无论在 Color 单元格中为审阅者分配的是何种颜色，在原始绘图页上输入的注释始终为黄色。</span><span class="sxs-lookup"><span data-stu-id="19418-108">Comments entered on the original drawing page are always colored yellow, regardless of the color assigned to a reviewer in the Color cell.</span></span> 
  
<span data-ttu-id="19418-109">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="19418-109">To get a reference to the Color cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="19418-110">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="19418-110">Cell name:</span></span>  <br/> | <span data-ttu-id="19418-111">Reviewer.Color [  *i*  ] 其中  *i*  = <1> 2， 3...</span><span class="sxs-lookup"><span data-stu-id="19418-111">Reviewer.Color [  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="19418-112">若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="19418-112">To get a reference to the Color cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="19418-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="19418-113">Section index:</span></span>  <br/> |<span data-ttu-id="19418-114">**visSectionReviewer**</span><span class="sxs-lookup"><span data-stu-id="19418-114">**visSectionReviewer**</span></span> <br/> |
| <span data-ttu-id="19418-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="19418-115">Row index:</span></span>  <br/> |<span data-ttu-id="19418-116">**visRowReviewer**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="19418-116">**visRowReviewer** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="19418-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="19418-117">Cell index:</span></span>  <br/> |<span data-ttu-id="19418-118">**visReviewerColor**</span><span class="sxs-lookup"><span data-stu-id="19418-118">**visReviewerColor**</span></span> <br/> |
   

