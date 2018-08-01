---
title: X Dynamics 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1145
localization_priority: Normal
ms.assetid: 9757dfb4-6d37-0517-17fe-7593ff12bbfe
description: 代表 x 的控制手柄的锚点在本地坐标系中的坐标。
ms.openlocfilehash: 9dee2381c15ed2817df9f89ebc830cf31bf64c1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781703"
---
# <a name="x-dynamics-cell-controls-section"></a><span data-ttu-id="a669b-103">X Dynamics 单元格（“Controls”部分）</span><span class="sxs-lookup"><span data-stu-id="a669b-103">X Dynamics Cell (Controls Section)</span></span>

<span data-ttu-id="a669b-104">代表*x*的控制手柄的锚点在本地坐标系中的坐标。</span><span class="sxs-lookup"><span data-stu-id="a669b-104">Represents the  *x*  -coordinate for a control handle's anchor point in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a669b-105">注释</span><span class="sxs-lookup"><span data-stu-id="a669b-105">Remarks</span></span>

<span data-ttu-id="a669b-106">锚点用于动态过程中类似橡皮筋的固定点。</span><span class="sxs-lookup"><span data-stu-id="a669b-106">The anchor point is used for rubber-banding during dynamics.</span></span>
  
<span data-ttu-id="a669b-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X Dynamics 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="a669b-107">To get a reference to the X Dynamics cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a669b-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="a669b-108">Cell name:</span></span>  <br/> | <span data-ttu-id="a669b-109">控件。</span><span class="sxs-lookup"><span data-stu-id="a669b-109">Controls.</span></span>  <span data-ttu-id="a669b-110">*名称*。XDynwhere 控件。</span><span class="sxs-lookup"><span data-stu-id="a669b-110">*name*  .XDynwhere Controls.</span></span>  <span data-ttu-id="a669b-111">*name*是控制行的名称。</span><span class="sxs-lookup"><span data-stu-id="a669b-111">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="a669b-112">要从某个程序按索引获取对 X Dynamics 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="a669b-112">To get a reference to the X Dynamics cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="a669b-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="a669b-113">Section index:</span></span>  <br/> |<span data-ttu-id="a669b-114">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="a669b-114">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="a669b-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="a669b-115">Row index:</span></span>  <br/> |<span data-ttu-id="a669b-116">**visRowControl** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="a669b-116">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="a669b-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="a669b-117">Cell index:</span></span>  <br/> |<span data-ttu-id="a669b-118">**visCtlXDyn**</span><span class="sxs-lookup"><span data-stu-id="a669b-118">**visCtlXDyn**</span></span> <br/> |
   

