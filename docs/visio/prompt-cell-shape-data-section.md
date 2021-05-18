---
title: Prompt 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251343
localization_priority: Normal
ms.assetid: 42f42d73-a00c-ca93-adc9-4f8869b9cd42
description: 指定当鼠标悬停在“形状数据”窗口中的某个值上时作为提示出现的说明性文本或指导性文本。
ms.openlocfilehash: 4ecb7eb5a1e775d2f3f5271476ef45cdf020d7c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405483"
---
# <a name="prompt-cell-shape-data-section"></a><span data-ttu-id="2dec5-103">Prompt 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="2dec5-103">Prompt Cell (Shape Data Section)</span></span>

<span data-ttu-id="2dec5-104">指定当鼠标悬停在 **“形状数据”** 窗口中的某个值上时作为提示出现的说明性文本或指导性文本。</span><span class="sxs-lookup"><span data-stu-id="2dec5-104">Specifies descriptive or instructional text that appears as a tip when the mouse is paused over a value in the **Shape Data** window.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="2dec5-105">备注</span><span class="sxs-lookup"><span data-stu-id="2dec5-105">Remarks</span></span>

<span data-ttu-id="2dec5-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Prompt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2dec5-106">To get a reference to the Prompt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2dec5-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2dec5-107">Cell name:</span></span>  <br/> | <span data-ttu-id="2dec5-108">Prop.  *名称*  。提示其中  *Name*  是行名称</span><span class="sxs-lookup"><span data-stu-id="2dec5-108">Prop.  *Name*  .Prompt where  *Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="2dec5-109">要从某个程序按索引获取对 Prompt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2dec5-109">To get a reference to the Prompt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2dec5-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2dec5-110">Section index:</span></span>  <br/> |<span data-ttu-id="2dec5-111">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="2dec5-111">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="2dec5-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="2dec5-112">Row index:</span></span>  <br/> |<span data-ttu-id="2dec5-113">**visRowProp +** *i*  其中  *i*  = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="2dec5-113">**visRowProp +** *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="2dec5-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2dec5-114">Cell index:</span></span>  <br/> |<span data-ttu-id="2dec5-115">**visCustPropsPrompt**</span><span class="sxs-lookup"><span data-stu-id="2dec5-115">**visCustPropsPrompt**</span></span> <br/> |
   

