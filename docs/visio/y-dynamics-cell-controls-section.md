---
title: Y Dynamics 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251284
localization_priority: Normal
ms.assetid: cb221974-2f1a-edb0-477b-39a3c4a64c56
description: 代表 y-控制手柄的锚点在本地坐标系中的坐标。 锚点用于动态过程中类似橡皮筋的固定点。
ms.openlocfilehash: 162f062d382f3f303ae39db725f3fbfa0790bfc4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781733"
---
# <a name="y-dynamics-cell-controls-section"></a><span data-ttu-id="08591-104">Y Dynamics 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="08591-104">Y Dynamics Cell (Controls Section)</span></span>

<span data-ttu-id="08591-105">代表*y* -控制手柄的锚点在本地坐标系中的坐标。</span><span class="sxs-lookup"><span data-stu-id="08591-105">Represents the  *y*  -coordinate for a control handle's anchor point in local coordinates.</span></span> <span data-ttu-id="08591-106">锚点用于动态过程中类似橡皮筋的固定点。</span><span class="sxs-lookup"><span data-stu-id="08591-106">The anchor point is used for rubber-banding during dynamics.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="08591-107">备注</span><span class="sxs-lookup"><span data-stu-id="08591-107">Remarks</span></span>

<span data-ttu-id="08591-108">要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y Dynamics 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="08591-108">To get a reference to the Y Dynamics cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08591-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="08591-109">Cell name:</span></span>  <br/> | <span data-ttu-id="08591-110">控件。</span><span class="sxs-lookup"><span data-stu-id="08591-110">Controls.</span></span>  <span data-ttu-id="08591-111">*名称*。YDynwhere 控件。</span><span class="sxs-lookup"><span data-stu-id="08591-111">*name*  .YDynwhere Controls.</span></span>  <span data-ttu-id="08591-112">*name*是控制行的名称。</span><span class="sxs-lookup"><span data-stu-id="08591-112">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="08591-113">若要从某个程序按索引获取对 Y Dynamics 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="08591-113">To get a reference to the Y Dynamics cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="08591-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="08591-114">Section index:</span></span>  <br/> |<span data-ttu-id="08591-115">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="08591-115">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="08591-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="08591-116">Row index:</span></span>  <br/> |<span data-ttu-id="08591-117">**visRowControl** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="08591-117">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="08591-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="08591-118">Cell index:</span></span>  <br/> |<span data-ttu-id="08591-119">**visCtlYDyn**</span><span class="sxs-lookup"><span data-stu-id="08591-119">**visCtlYDyn**</span></span> <br/> |
   

