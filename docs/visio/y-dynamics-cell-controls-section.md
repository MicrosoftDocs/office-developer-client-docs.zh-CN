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
description: 表示控制手柄的定位点在本地坐标中的 y 坐标。 锚点用于动态过程中类似橡皮筋的固定点。
ms.openlocfilehash: 13d463ebccd9cc7a23641a036dc5dd967513b07f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404825"
---
# <a name="y-dynamics-cell-controls-section"></a><span data-ttu-id="0e312-104">Y Dynamics 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="0e312-104">Y Dynamics Cell (Controls Section)</span></span>

<span data-ttu-id="0e312-105">表示控制手柄的定位点在本地坐标中的  *y*  坐标。</span><span class="sxs-lookup"><span data-stu-id="0e312-105">Represents the  *y*  -coordinate for a control handle's anchor point in local coordinates.</span></span> <span data-ttu-id="0e312-106">锚点用于动态过程中类似橡皮筋的固定点。</span><span class="sxs-lookup"><span data-stu-id="0e312-106">The anchor point is used for rubber-banding during dynamics.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0e312-107">备注</span><span class="sxs-lookup"><span data-stu-id="0e312-107">Remarks</span></span>

<span data-ttu-id="0e312-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y Dynamics 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="0e312-108">To get a reference to the Y Dynamics cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0e312-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="0e312-109">Cell name:</span></span>  <br/> | <span data-ttu-id="0e312-110">控件。</span><span class="sxs-lookup"><span data-stu-id="0e312-110">Controls.</span></span>  <span data-ttu-id="0e312-111">*name*  .YDynwhere Controls.</span><span class="sxs-lookup"><span data-stu-id="0e312-111">*name*  .YDynwhere Controls.</span></span>  <span data-ttu-id="0e312-112">*name*  是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="0e312-112">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="0e312-113">要从某个程序按索引获取对 Y Dynamics 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="0e312-113">To get a reference to the Y Dynamics cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="0e312-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="0e312-114">Section index:</span></span>  <br/> |<span data-ttu-id="0e312-115">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="0e312-115">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="0e312-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="0e312-116">Row index:</span></span>  <br/> |<span data-ttu-id="0e312-117">**visRowControl**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="0e312-117">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="0e312-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="0e312-118">Cell index:</span></span>  <br/> |<span data-ttu-id="0e312-119">**visCtlYDyn**</span><span class="sxs-lookup"><span data-stu-id="0e312-119">**visCtlYDyn**</span></span> <br/> |
   

