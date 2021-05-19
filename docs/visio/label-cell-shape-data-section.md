---
title: Label 单元格（“形状数据”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm510
localization_priority: Normal
ms.assetid: 6d328b1c-8d92-eb1a-7317-7dd85c674ff9
description: 指定在“形状数据”窗口中向用户显示的标签。标签由字母数字字符组成，包括下划线 (_) 字符。
ms.openlocfilehash: d341acfbd47446a5b6dbee51ed821d1e1f34e15d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420176"
---
# <a name="label-cell-shape-data-section"></a><span data-ttu-id="704e1-104">Label 单元格（“形状数据”内容）</span><span class="sxs-lookup"><span data-stu-id="704e1-104">Label Cell (Shape Data Section)</span></span>

<span data-ttu-id="704e1-p102">指定在 **“形状数据”** 窗口中向用户显示的标签。标签由字母数字字符组成，包括下划线 (_) 字符。</span><span class="sxs-lookup"><span data-stu-id="704e1-p102">Specifies the label that appears to users in the **Shape Data** window. A label consists of alphanumeric characters, including the underscore (_) character.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="704e1-107">备注</span><span class="sxs-lookup"><span data-stu-id="704e1-107">Remarks</span></span>

<span data-ttu-id="704e1-108">该应用程序会自动将标签字符串用引号引起来放在单元格中，但引号并不显示在 **“形状数据”** 窗口中。</span><span class="sxs-lookup"><span data-stu-id="704e1-108">The application automatically encloses the Label string in quotation marks in the cell, but the quotation marks are not displayed in the **Shape Data** window.</span></span> 
  
<span data-ttu-id="704e1-109">如果没有找到标签文本，Visio 将在 **“形状数据”** 窗口中显示行名称 (Prop.Row)。</span><span class="sxs-lookup"><span data-stu-id="704e1-109">If no label text is found, Visio displays the row name (Prop.Row) in the **Shape Data** window.</span></span> 
  
<span data-ttu-id="704e1-110">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Label 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="704e1-110">To get a reference to the Label cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="704e1-111">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="704e1-111">Cell name:</span></span>  <br/> |<span data-ttu-id="704e1-112">Prop. *Name*  .标签，其中 Prop.  *Name*  是行名称</span><span class="sxs-lookup"><span data-stu-id="704e1-112">Prop. *Name*  .Label where Prop.  *Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="704e1-113">若要从某个程序按索引获取对 Label 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="704e1-113">To get a reference to the Label cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="704e1-114">内容索引：</span><span class="sxs-lookup"><span data-stu-id="704e1-114">Section index:</span></span>  <br/> |<span data-ttu-id="704e1-115">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="704e1-115">**visSectionProp**</span></span> <br/> |
|<span data-ttu-id="704e1-116">行索引：</span><span class="sxs-lookup"><span data-stu-id="704e1-116">Row index:</span></span>  <br/> |<span data-ttu-id="704e1-117">**visRowProp**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="704e1-117">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
|<span data-ttu-id="704e1-118">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="704e1-118">Cell index:</span></span>  <br/> |<span data-ttu-id="704e1-119">**visCustPropsLabel**</span><span class="sxs-lookup"><span data-stu-id="704e1-119">**visCustPropsLabel**</span></span> <br/> |
   

