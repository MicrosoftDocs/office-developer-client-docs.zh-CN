---
title: X 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251281
localization_priority: Normal
ms.assetid: b7aea554-f491-6a9a-4d07-feeab739a9df
description: 表示表示形状的控制手柄在本地坐标系中的位置的 x 坐标。
ms.openlocfilehash: 58eea4e9c3cfe127c4adcc7fb75e395f53874dd9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32269781"
---
# <a name="x-cell-controls-section"></a><span data-ttu-id="24745-103">X 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="24745-103">X Cell (Controls Section)</span></span>

<span data-ttu-id="24745-104">表示表示形状的控制手柄在本地坐标系中的位置的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="24745-104">Represents the  *x*  -coordinate that indicates the location of a shape's control handle in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="24745-105">注解</span><span class="sxs-lookup"><span data-stu-id="24745-105">Remarks</span></span>

<span data-ttu-id="24745-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="24745-106">To get a reference to the X cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="24745-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="24745-107">Cell name:</span></span>  <br/> | <span data-ttu-id="24745-108">措施.</span><span class="sxs-lookup"><span data-stu-id="24745-108">Controls.</span></span>  <span data-ttu-id="24745-109">*名称*。X where 控件。</span><span class="sxs-lookup"><span data-stu-id="24745-109">*name*  .X where Controls.</span></span>  <span data-ttu-id="24745-110">*名称*是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="24745-110">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="24745-111">要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="24745-111">To get a reference to the X cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="24745-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="24745-112">Section index:</span></span>  <br/> |<span data-ttu-id="24745-113">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="24745-113">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="24745-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="24745-114">Row index:</span></span>  <br/> |<span data-ttu-id="24745-115">**visRowControl** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="24745-115">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="24745-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="24745-116">Cell index:</span></span>  <br/> |<span data-ttu-id="24745-117">**visCtlX**</span><span class="sxs-lookup"><span data-stu-id="24745-117">**visCtlX**</span></span> <br/> |
   

