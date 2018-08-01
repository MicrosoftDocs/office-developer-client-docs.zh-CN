---
title: X 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1028735
localization_priority: Normal
ms.assetid: f9db8623-9fcf-7037-2d11-d509f463025d
description: X-的页坐标中注释标记的坐标。
ms.openlocfilehash: 454c28c6f15c705148155751d533a516aae7d2d0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781668"
---
# <a name="x-cell-annotation-section"></a><span data-ttu-id="9dad9-103">X 单元格（“Annotation”部分）</span><span class="sxs-lookup"><span data-stu-id="9dad9-103">X Cell (Annotation Section)</span></span>

<span data-ttu-id="9dad9-104">*X* -坐标的页坐标中注释标记。</span><span class="sxs-lookup"><span data-stu-id="9dad9-104">The  *x*  -coordinate of the comment marker in page coordinates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9dad9-105">此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。</span><span class="sxs-lookup"><span data-stu-id="9dad9-105">This cell is used for tracking comments only when opening a .vsd file in Microsoft Visio 2013 or when saving a .vsdx file in the .vsd file format.</span></span> <span data-ttu-id="9dad9-106">它不用于跟踪.vsdx Visio 2013 中的文档中的注释。</span><span class="sxs-lookup"><span data-stu-id="9dad9-106">It is not used for tracking comments in .vsdx documents in Visio 2013.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="9dad9-107">说明</span><span class="sxs-lookup"><span data-stu-id="9dad9-107">Remarks</span></span>

<span data-ttu-id="9dad9-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="9dad9-108">To get a reference to the X cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9dad9-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="9dad9-109">Cell name:</span></span>  <br/> | <span data-ttu-id="9dad9-110">Annotation.X [ *i* ] 其中*i* = < 1 >，2，3...</span><span class="sxs-lookup"><span data-stu-id="9dad9-110">Annotation.X[  *i*  ]            where  *i*  = <1>, 2, 3...</span></span>  <br/> |
   
<span data-ttu-id="9dad9-111">要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="9dad9-111">To get a reference to the X cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="9dad9-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="9dad9-112">Section index:</span></span>  <br/> |<span data-ttu-id="9dad9-113">**visSectionAnnotation**</span><span class="sxs-lookup"><span data-stu-id="9dad9-113">**visSectionAnnotation**</span></span> <br/> |
| <span data-ttu-id="9dad9-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="9dad9-114">Row index:</span></span>  <br/> |<span data-ttu-id="9dad9-115">**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="9dad9-115">**visRowAnnotation** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="9dad9-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="9dad9-116">Cell index:</span></span>  <br/> |<span data-ttu-id="9dad9-117">**visAnnotationX**</span><span class="sxs-lookup"><span data-stu-id="9dad9-117">**visAnnotationX**</span></span> <br/> |
   

