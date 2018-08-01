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
ms.openlocfilehash: 1e11a8c7c680dd53ad7cd9f6877fe29eb34a7b53
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780978"
---
# <a name="prompt-cell-shape-data-section"></a><span data-ttu-id="cf91b-103">Prompt 单元格（“Shape Data”部分）</span><span class="sxs-lookup"><span data-stu-id="cf91b-103">Prompt Cell (Shape Data Section)</span></span>

<span data-ttu-id="cf91b-104">指定当鼠标悬停在 **“形状数据”** 窗口中的某个值上时作为提示出现的说明性文本或指导性文本。</span><span class="sxs-lookup"><span data-stu-id="cf91b-104">Specifies descriptive or instructional text that appears as a tip when the mouse is paused over a value in the **Shape Data** window.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cf91b-105">说明</span><span class="sxs-lookup"><span data-stu-id="cf91b-105">Remarks</span></span>

<span data-ttu-id="cf91b-106">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Prompt 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="cf91b-106">To get a reference to the Prompt cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cf91b-107">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="cf91b-107">Cell name:</span></span>  <br/> | <span data-ttu-id="cf91b-108">属性。 *名称*。提示其中*Name*是行名称</span><span class="sxs-lookup"><span data-stu-id="cf91b-108">Prop.  *Name*  .Prompt where  *Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="cf91b-109">要从某个程序按索引获取对 Prompt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="cf91b-109">To get a reference to the Prompt cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="cf91b-110">内容索引：</span><span class="sxs-lookup"><span data-stu-id="cf91b-110">Section index:</span></span>  <br/> |<span data-ttu-id="cf91b-111">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="cf91b-111">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="cf91b-112">行索引：</span><span class="sxs-lookup"><span data-stu-id="cf91b-112">Row index:</span></span>  <br/> |<span data-ttu-id="cf91b-113">**visRowProp +***i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="cf91b-113">**visRowProp +** *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="cf91b-114">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="cf91b-114">Cell index:</span></span>  <br/> |<span data-ttu-id="cf91b-115">**visCustPropsPrompt**</span><span class="sxs-lookup"><span data-stu-id="cf91b-115">**visCustPropsPrompt**</span></span> <br/> |
   

