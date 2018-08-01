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
description: 代表 y-指示形状的控制手柄在本地坐标系中的位置的坐标。
ms.openlocfilehash: 8104ae6d647feb4e1b83474b63f40e243e5405e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781699"
---
# <a name="y-cell-controls-section"></a><span data-ttu-id="f55b6-103">Y 单元格（“Controls”部分）</span><span class="sxs-lookup"><span data-stu-id="f55b6-103">Y Cell (Controls Section)</span></span>

<span data-ttu-id="f55b6-104">代表*y* -指示形状的控制手柄在本地坐标系中的位置的坐标。</span><span class="sxs-lookup"><span data-stu-id="f55b6-104">Represents the  *y*  -coordinate that indicates the location of a shape's control handle in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f55b6-105">说明</span><span class="sxs-lookup"><span data-stu-id="f55b6-105">Remarks</span></span>

<span data-ttu-id="f55b6-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="f55b6-106">To get a reference to the Y cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f55b6-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="f55b6-107">Cell name:</span></span>  <br/> | <span data-ttu-id="f55b6-108">控件。</span><span class="sxs-lookup"><span data-stu-id="f55b6-108">Controls.</span></span>  <span data-ttu-id="f55b6-109">*名称*。Ywhere 控件。</span><span class="sxs-lookup"><span data-stu-id="f55b6-109">*name*  .Ywhere Controls.</span></span>  <span data-ttu-id="f55b6-110">*name*是控制行的名称。</span><span class="sxs-lookup"><span data-stu-id="f55b6-110">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="f55b6-111">要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="f55b6-111">To get a reference to the Y cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="f55b6-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="f55b6-112">Section index:</span></span>  <br/> |<span data-ttu-id="f55b6-113">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="f55b6-113">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="f55b6-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="f55b6-114">Row index:</span></span>  <br/> |<span data-ttu-id="f55b6-115">**visRowControl** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="f55b6-115">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="f55b6-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="f55b6-116">Cell index:</span></span>  <br/> |<span data-ttu-id="f55b6-117">**visCtlY**</span><span class="sxs-lookup"><span data-stu-id="f55b6-117">**visCtlY**</span></span> <br/> |
   

