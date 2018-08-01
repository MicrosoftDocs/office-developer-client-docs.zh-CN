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
description: 代表 x-指示形状的控制手柄在本地坐标系中的位置的坐标。
ms.openlocfilehash: e47b26c72709a2ee74675e73b8e8424bbfb325e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781679"
---
# <a name="x-cell-controls-section"></a><span data-ttu-id="19f31-103">X 单元格（“Controls”部分）</span><span class="sxs-lookup"><span data-stu-id="19f31-103">X Cell (Controls Section)</span></span>

<span data-ttu-id="19f31-104">代表*x* -指示形状的控制手柄在本地坐标系中的位置的坐标。</span><span class="sxs-lookup"><span data-stu-id="19f31-104">Represents the  *x*  -coordinate that indicates the location of a shape's control handle in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="19f31-105">说明</span><span class="sxs-lookup"><span data-stu-id="19f31-105">Remarks</span></span>

<span data-ttu-id="19f31-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="19f31-106">To get a reference to the X cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="19f31-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="19f31-107">Cell name:</span></span>  <br/> | <span data-ttu-id="19f31-108">控件。</span><span class="sxs-lookup"><span data-stu-id="19f31-108">Controls.</span></span>  <span data-ttu-id="19f31-109">*名称*。其中 x 控件。</span><span class="sxs-lookup"><span data-stu-id="19f31-109">*name*  .X where Controls.</span></span>  <span data-ttu-id="19f31-110">*name*是控制行的名称。</span><span class="sxs-lookup"><span data-stu-id="19f31-110">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="19f31-111">要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="19f31-111">To get a reference to the X cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="19f31-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="19f31-112">Section index:</span></span>  <br/> |<span data-ttu-id="19f31-113">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="19f31-113">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="19f31-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="19f31-114">Row index:</span></span>  <br/> |<span data-ttu-id="19f31-115">**visRowControl** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="19f31-115">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="19f31-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="19f31-116">Cell index:</span></span>  <br/> |<span data-ttu-id="19f31-117">**visCtlX**</span><span class="sxs-lookup"><span data-stu-id="19f31-117">**visCtlX**</span></span> <br/> |
   

