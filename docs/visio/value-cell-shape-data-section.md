---
title: Value 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1090
localization_priority: Normal
ms.assetid: fd42a6ce-f621-4e9e-aba3-23a1b87a5651
description: 包含与在“定义形状数据”对话框中输入的形状数据项值相同的值。
ms.openlocfilehash: 5b373149360167585fc5a143ce9458703e219045
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781628"
---
# <a name="value-cell-shape-data-section"></a><span data-ttu-id="411cc-103">Value 单元格（“Shape Data”部分）</span><span class="sxs-lookup"><span data-stu-id="411cc-103">Value Cell (Shape Data Section)</span></span>

<span data-ttu-id="411cc-104">包含与在 **“定义形状数据”** 对话框中输入的形状数据项值相同的值。</span><span class="sxs-lookup"><span data-stu-id="411cc-104">Contains the shape data item's value as entered in the **Define Shape Data** dialog box.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="411cc-105">说明</span><span class="sxs-lookup"><span data-stu-id="411cc-105">Remarks</span></span>

<span data-ttu-id="411cc-p101">在 **“定义形状数据”** 对话框中输入的值将取代在此单元格中输入的公式。即使使用 GUARD 函数保护该公式，也同样会取代。</span><span class="sxs-lookup"><span data-stu-id="411cc-p101">Formulas entered in this cell are overridden by values entered in the **Define Shape Data** dialog box. This is true even if you use the GUARD function to protect the formula.</span></span> 
  
<span data-ttu-id="411cc-108">若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Value 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="411cc-108">To get a reference to the Value cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="411cc-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="411cc-109">Cell name:</span></span>  <br/> | <span data-ttu-id="411cc-110">属性。 *名称*。值其中属性。 *Name*是行名称</span><span class="sxs-lookup"><span data-stu-id="411cc-110">Prop.  *Name*  .Value where Prop.  *Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="411cc-111">若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="411cc-111">To get a reference to the Value cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="411cc-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="411cc-112">Section index:</span></span>  <br/> |<span data-ttu-id="411cc-113">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="411cc-113">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="411cc-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="411cc-114">Row index:</span></span>  <br/> |<span data-ttu-id="411cc-115">**visRowProp** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="411cc-115">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="411cc-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="411cc-116">Cell index:</span></span>  <br/> |<span data-ttu-id="411cc-117">**visCustPropsValue**</span><span class="sxs-lookup"><span data-stu-id="411cc-117">**visCustPropsValue**</span></span> <br/> |
   

