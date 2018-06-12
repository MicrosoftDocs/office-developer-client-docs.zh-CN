---
title: Y 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60095
localization_priority: Normal
ms.assetid: 527a4615-2013-a4b4-81cd-7f5d71c1803c
description: Y-坐标的页坐标中注释标记。
ms.openlocfilehash: cc2399de7919512796a39ca39c705c214f4c51a2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781694"
---
# <a name="y-cell-annotation-section"></a><span data-ttu-id="dc685-103">Y 单元格（“Annotation”内容）</span><span class="sxs-lookup"><span data-stu-id="dc685-103">Y Cell (Annotation Section)</span></span>

<span data-ttu-id="dc685-104">*Y* -坐标的页坐标中注释标记。</span><span class="sxs-lookup"><span data-stu-id="dc685-104">The  *y*  -coordinate of the comment marker in page coordinates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dc685-105">此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。</span><span class="sxs-lookup"><span data-stu-id="dc685-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="dc685-106">它不用于跟踪.vsdx Visio 2013 中的文档中的注释。</span><span class="sxs-lookup"><span data-stu-id="dc685-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="dc685-107">备注</span><span class="sxs-lookup"><span data-stu-id="dc685-107">Remarks</span></span>

<span data-ttu-id="dc685-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="dc685-108">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dc685-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="dc685-109">Cell name:</span></span>  <br/> | <span data-ttu-id="dc685-110">Annotation.Y [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="dc685-110">Annotation.Y [  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="dc685-111">若要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="dc685-111">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="dc685-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="dc685-112">Section index:</span></span>  <br/> |<span data-ttu-id="dc685-113">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="dc685-113">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="dc685-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="dc685-114">Row index:</span></span>  <br/> |<span data-ttu-id="dc685-115">**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="dc685-115">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="dc685-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="dc685-116">Cell index:</span></span>  <br/> |<span data-ttu-id="dc685-117">**visAnnotationY**</span><span class="sxs-lookup"><span data-stu-id="dc685-117">**visAnnotationY**</span></span> <br/> |
   

