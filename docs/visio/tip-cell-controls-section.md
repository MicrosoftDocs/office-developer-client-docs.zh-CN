---
title: Tip 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1010
localization_priority: Normal
ms.assetid: 7fd11650-fffa-1316-d302-3122ac5feb14
description: 表示说明性文本字符串，当用户将指针停留在形状的控制手柄之上时，说明性的文本字符串就作为工具提示显示出来。应用程序在单元格中自动用引号引起提示字符串，但引号不会在工具提示中显示出来。
ms.openlocfilehash: b9b0c19aff5e3ab8a4c1e29d319eb42f7ee4a271
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424859"
---
# <a name="tip-cell-controls-section"></a><span data-ttu-id="6ed9d-104">Tip 单元格（“Controls”内容）</span><span class="sxs-lookup"><span data-stu-id="6ed9d-104">Tip Cell (Controls Section)</span></span>

<span data-ttu-id="6ed9d-p102">表示说明性文本字符串，当用户将指针停留在形状的控制手柄之上时，说明性的文本字符串就作为工具提示显示出来。应用程序在单元格中自动用引号引起提示字符串，但引号不会在工具提示中显示出来。</span><span class="sxs-lookup"><span data-stu-id="6ed9d-p102">Represents a descriptive text string that appears as a tool tip when a user pauses the pointer over a shape's control handle. The application automatically encloses the tip string in quotation marks in the cell, but the quotation marks are not displayed in the tool tip.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6ed9d-107">备注</span><span class="sxs-lookup"><span data-stu-id="6ed9d-107">Remarks</span></span>

<span data-ttu-id="6ed9d-108">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Tip 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="6ed9d-108">To get a reference to the Tip cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6ed9d-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="6ed9d-109">Cell name:</span></span>  <br/> | <span data-ttu-id="6ed9d-110">控件。</span><span class="sxs-lookup"><span data-stu-id="6ed9d-110">Controls.</span></span>  <span data-ttu-id="6ed9d-111">*name*  .提示控件。</span><span class="sxs-lookup"><span data-stu-id="6ed9d-111">*name*  .Tipwhere Controls.</span></span>  <span data-ttu-id="6ed9d-112">*name*  是控件行的名称。</span><span class="sxs-lookup"><span data-stu-id="6ed9d-112">*name*  is the name of the controls row.</span></span>  <br/> |
   
<span data-ttu-id="6ed9d-113">要从某个程序按索引获取对 Tip 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="6ed9d-113">To get a reference to the Tip cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="6ed9d-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="6ed9d-114">Section index:</span></span>  <br/> |<span data-ttu-id="6ed9d-115">**visSectionControls**</span><span class="sxs-lookup"><span data-stu-id="6ed9d-115">**visSectionControls**</span></span> <br/> |
| <span data-ttu-id="6ed9d-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="6ed9d-116">Row index:</span></span>  <br/> |<span data-ttu-id="6ed9d-117">**visRowControl**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="6ed9d-117">**visRowControl** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="6ed9d-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="6ed9d-118">Cell index:</span></span>  <br/> |<span data-ttu-id="6ed9d-119">**visCtlTip**</span><span class="sxs-lookup"><span data-stu-id="6ed9d-119">**visCtlTip**</span></span> <br/> |
   

