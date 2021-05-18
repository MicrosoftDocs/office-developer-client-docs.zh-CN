---
title: Y 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251282
localization_priority: Normal
ms.assetid: dd7ea5fa-1d34-44e8-5a29-69ca542aecba
description: 表示 y 坐标，该坐标指示形状的控制手柄在本地坐标中的位置。
ms.openlocfilehash: 14aaa7aef7e7250baeb8ffb863244ece26a201e7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407947"
---
# <a name="y-cell-controls-section"></a><span data-ttu-id="6c310-103">Y 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="6c310-103">Y Cell (Controls Section)</span></span>

<span data-ttu-id="6c310-104">表示  *y*  坐标，该坐标指示形状的控制手柄在本地坐标中的位置。</span><span class="sxs-lookup"><span data-stu-id="6c310-104">Represents the  *y*  -coordinate that indicates the location of a shape's control handle in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="6c310-105">备注</span><span class="sxs-lookup"><span data-stu-id="6c310-105">Remarks</span></span>

<span data-ttu-id="6c310-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6c310-106">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6c310-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6c310-107">Cell name:</span></span>  <br/> | <span data-ttu-id="6c310-108">控件。</span><span class="sxs-lookup"><span data-stu-id="6c310-108">Controls.</span></span>  <span data-ttu-id="6c310-109">*name*  .Ywhere Controls.</span><span class="sxs-lookup"><span data-stu-id="6c310-109">*name*  .Ywhere Controls.</span></span>  <span data-ttu-id="6c310-110">*name*  是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="6c310-110">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="6c310-111">要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6c310-111">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6c310-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6c310-112">Section index:</span></span>  <br/> |<span data-ttu-id="6c310-113">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="6c310-113">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="6c310-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="6c310-114">Row index:</span></span>  <br/> |<span data-ttu-id="6c310-115">**visRowControl**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="6c310-115">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="6c310-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6c310-116">Cell index:</span></span>  <br/> |<span data-ttu-id="6c310-117">**visCtlY**</span><span class="sxs-lookup"><span data-stu-id="6c310-117">**visCtlY**</span></span> <br/> |
   

