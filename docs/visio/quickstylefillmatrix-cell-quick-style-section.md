---
title: QuickStyleFillMatrix 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8513cf3f-42bd-4e76-bfa8-8bf12f0d1296
description: 确定形状继承自活动主题的快速样式填充样式 (从0-6 的整数)。
ms.openlocfilehash: fca0d9f8fe58fdc7c227e9c093b418ffef1ccb52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417887"
---
# <a name="quickstylefillmatrix-cell-quick-style-section"></a><span data-ttu-id="6d3d9-103">QuickStyleFillMatrix 单元格 ("快速样式" 部分)</span><span class="sxs-lookup"><span data-stu-id="6d3d9-103">QuickStyleFillMatrix Cell (Quick Style Section)</span></span>

<span data-ttu-id="6d3d9-104">确定形状继承自活动主题的快速样式填充样式 (从0-6 的整数)。</span><span class="sxs-lookup"><span data-stu-id="6d3d9-104">Determines the Quick Style fill style that the shape inherits from the active theme, as an integer from 0-6.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="6d3d9-105">说明</span><span class="sxs-lookup"><span data-stu-id="6d3d9-105">Remarks</span></span>

<span data-ttu-id="6d3d9-106">若要从另一个公式按名称获取对**QuickStyleFillMatrix**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-106">To get a reference to the **QuickStyleFillMatrix** cell by name from another formula, by value of the **N** attribute of a **Cell** element, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6d3d9-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6d3d9-107">Cell name:</span></span>  <br/> | <span data-ttu-id="6d3d9-108">QuickStyleFillMatrix</span><span class="sxs-lookup"><span data-stu-id="6d3d9-108">QuickStyleFillMatrix</span></span>  <br/> |
   
<span data-ttu-id="6d3d9-109">若要从某个程序按索引获取对**QuickStyleFillMatrix**单元格的引用, 请使用带下列参数的**CellsSRC**属性:</span><span class="sxs-lookup"><span data-stu-id="6d3d9-109">To get a reference to the **QuickStyleFillMatrix** cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6d3d9-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6d3d9-110">Section index:</span></span>  <br/> |<span data-ttu-id="6d3d9-111">**visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="6d3d9-111">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="6d3d9-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="6d3d9-112">Row index:</span></span>  <br/> |<span data-ttu-id="6d3d9-113">**visRowQuickStyleProperties**</span><span class="sxs-lookup"><span data-stu-id="6d3d9-113">**visRowQuickStyleProperties**</span></span> <br/> |
| <span data-ttu-id="6d3d9-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6d3d9-114">Cell index:</span></span>  <br/> |<span data-ttu-id="6d3d9-115">**visQuickStyleFillMatrix**</span><span class="sxs-lookup"><span data-stu-id="6d3d9-115">**visQuickStyleFillMatrix**</span></span> <br/> |
   

