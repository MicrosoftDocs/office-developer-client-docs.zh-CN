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
description: 表示控制手柄的锚点在本地坐标系中的 x 坐标。
ms.openlocfilehash: 7aef1fe779ae9b862e88eccf0112eb8696377858
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322300"
---
# <a name="x-dynamics-cell-controls-section"></a><span data-ttu-id="1b709-103">X Dynamics 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="1b709-103">X Dynamics Cell (Controls Section)</span></span>

<span data-ttu-id="1b709-104">表示控制手柄的锚点在本地坐标系中的*x*坐标。</span><span class="sxs-lookup"><span data-stu-id="1b709-104">Represents the  *x*  -coordinate for a control handle's anchor point in local coordinates.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1b709-105">注解</span><span class="sxs-lookup"><span data-stu-id="1b709-105">Remarks</span></span>

<span data-ttu-id="1b709-106">锚点用于动态过程中类似橡皮筋的固定点。</span><span class="sxs-lookup"><span data-stu-id="1b709-106">The anchor point is used for rubber-banding during dynamics.</span></span>
  
<span data-ttu-id="1b709-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X Dynamics 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="1b709-107">To get a reference to the X Dynamics cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1b709-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="1b709-108">Cell name:</span></span>  <br/> | <span data-ttu-id="1b709-109">措施.</span><span class="sxs-lookup"><span data-stu-id="1b709-109">Controls.</span></span>  <span data-ttu-id="1b709-110">*名称*。XDynwhere 控件。</span><span class="sxs-lookup"><span data-stu-id="1b709-110">*name*  .XDynwhere Controls.</span></span>  <span data-ttu-id="1b709-111">*名称*是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="1b709-111">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="1b709-112">要从某个程序按索引获取对 X Dynamics 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="1b709-112">To get a reference to the X Dynamics cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="1b709-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="1b709-113">Section index:</span></span>  <br/> |<span data-ttu-id="1b709-114">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="1b709-114">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="1b709-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="1b709-115">Row index:</span></span>  <br/> |<span data-ttu-id="1b709-116">**visRowControl** +  *i* = \*\* 0、1、2 .。。</span><span class="sxs-lookup"><span data-stu-id="1b709-116">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="1b709-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="1b709-117">Cell index:</span></span>  <br/> |<span data-ttu-id="1b709-118">**visCtlXDyn**</span><span class="sxs-lookup"><span data-stu-id="1b709-118">**visCtlXDyn**</span></span> <br/> |
   

