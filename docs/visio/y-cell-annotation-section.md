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
description: 页面坐标中注释标记的 y 坐标。
ms.openlocfilehash: 48a37c261078cd1000331920b33549cee2c1da03
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429199"
---
# <a name="y-cell-annotation-section"></a><span data-ttu-id="f90a2-103">Y 单元格（“Annotation”内容）</span><span class="sxs-lookup"><span data-stu-id="f90a2-103">Y Cell (Annotation Section)</span></span>

<span data-ttu-id="f90a2-104">页面坐标中注释标记的*y*坐标。</span><span class="sxs-lookup"><span data-stu-id="f90a2-104">The  *y*  -coordinate of the comment marker in page coordinates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f90a2-105">仅当在 Microsoft Visio 2013 中打开 .vsd 文件或以 .vsd 文件格式保存 .vsdx 文件时, 才会使用此单元格进行跟踪注释。</span><span class="sxs-lookup"><span data-stu-id="f90a2-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="f90a2-106">它不用于跟踪在 Visio 2013 中的 .vsdx 文档中的注释。</span><span class="sxs-lookup"><span data-stu-id="f90a2-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f90a2-107">说明</span><span class="sxs-lookup"><span data-stu-id="f90a2-107">Remarks</span></span>

<span data-ttu-id="f90a2-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f90a2-108">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f90a2-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f90a2-109">Cell name:</span></span>  <br/> | <span data-ttu-id="f90a2-110">批注。 Y [ *i* ] 其中*i* = <1>, 2, 3 .。。</span><span class="sxs-lookup"><span data-stu-id="f90a2-110">Annotation.Y [  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="f90a2-111">要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f90a2-111">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f90a2-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f90a2-112">Section index:</span></span>  <br/> |<span data-ttu-id="f90a2-113">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="f90a2-113">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="f90a2-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="f90a2-114">Row index:</span></span>  <br/> |<span data-ttu-id="f90a2-115">**visRowAnnotation** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="f90a2-115">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="f90a2-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f90a2-116">Cell index:</span></span>  <br/> |<span data-ttu-id="f90a2-117">**visAnnotationY**</span><span class="sxs-lookup"><span data-stu-id="f90a2-117">**visAnnotationY**</span></span> <br/> |
   

