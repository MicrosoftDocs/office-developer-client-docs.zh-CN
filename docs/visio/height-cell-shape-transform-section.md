---
title: Height 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251195
localization_priority: Normal
ms.assetid: 194d5beb-c705-f567-84de-8305c41081a8
description: 确定以绘图单位表示的形状的高度。
ms.openlocfilehash: 1f08fec0ec09e4ba77296495defc91b0f1f3a4c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422864"
---
# <a name="height-cell-shape-transform-section"></a><span data-ttu-id="498d6-103">Height 单元格（“Shape Transform”内容）</span><span class="sxs-lookup"><span data-stu-id="498d6-103">Height Cell (Shape Transform Section)</span></span>

<span data-ttu-id="498d6-104">确定以绘图单位表示的形状的高度。</span><span class="sxs-lookup"><span data-stu-id="498d6-104">Determines the height of the shape in drawing units.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="498d6-105">说明</span><span class="sxs-lookup"><span data-stu-id="498d6-105">Remarks</span></span>

<span data-ttu-id="498d6-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Height 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="498d6-106">To get a reference to the Height cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="498d6-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="498d6-107">Cell name:</span></span>  <br/> | <span data-ttu-id="498d6-108">Height</span><span class="sxs-lookup"><span data-stu-id="498d6-108">Height</span></span>  <br/> |
   
<span data-ttu-id="498d6-109">要从某个程序按索引获取对 Height 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="498d6-109">To get a reference to the Height cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="498d6-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="498d6-110">Section index:</span></span>  <br/> |<span data-ttu-id="498d6-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="498d6-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="498d6-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="498d6-112">Row index:</span></span>  <br/> |<span data-ttu-id="498d6-113">**visRowXFormOut**</span><span class="sxs-lookup"><span data-stu-id="498d6-113">**visRowXFormOut**</span></span> <br/> |
| <span data-ttu-id="498d6-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="498d6-114">Cell index:</span></span>  <br/> |<span data-ttu-id="498d6-115">**visXFormHeight**</span><span class="sxs-lookup"><span data-stu-id="498d6-115">**visXFormHeight**</span></span> <br/> |
   

