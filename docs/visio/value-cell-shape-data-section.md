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
description: 在定义形状数据对话框中输入包含形状数据项的值。
ms.openlocfilehash: 5b373149360167585fc5a143ce9458703e219045
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781628"
---
# <a name="value-cell-shape-data-section"></a><span data-ttu-id="5fb69-103">Value 单元格（“Shape Data”内容）</span><span class="sxs-lookup"><span data-stu-id="5fb69-103">Value Cell (Shape Data Section)</span></span>

<span data-ttu-id="5fb69-104">在**定义形状数据**对话框中输入包含形状数据项的值。</span><span class="sxs-lookup"><span data-stu-id="5fb69-104">Contains the shape data item's value as entered in the **Define Shape Data** dialog box.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="5fb69-105">备注</span><span class="sxs-lookup"><span data-stu-id="5fb69-105">Remarks</span></span>

<span data-ttu-id="5fb69-106">在**定义形状数据**对话框中输入值的情况下，输入此单元格中的公式所替代。</span><span class="sxs-lookup"><span data-stu-id="5fb69-106">Formulas entered in this cell are overridden by values entered in the **Define Shape Data** dialog box.</span></span> <span data-ttu-id="5fb69-107">即使您使用 GUARD 函数保护公式，也是如此。</span><span class="sxs-lookup"><span data-stu-id="5fb69-107">This is true even if you use the GUARD function to protect the formula.</span></span> 
  
<span data-ttu-id="5fb69-108">若要获取对 Value 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用：</span><span class="sxs-lookup"><span data-stu-id="5fb69-108">To get a reference to the Value cell by name from another formula, or from a program by using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5fb69-109">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="5fb69-109">Cell name:</span></span>  <br/> | <span data-ttu-id="5fb69-110">属性。 *名称*。值其中属性。 *Name*是行名称</span><span class="sxs-lookup"><span data-stu-id="5fb69-110">Prop.  *Name*  .Value where Prop.  *Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="5fb69-111">若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的**CellsSRC**属性：</span><span class="sxs-lookup"><span data-stu-id="5fb69-111">To get a reference to the Value cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="5fb69-112">内容索引：</span><span class="sxs-lookup"><span data-stu-id="5fb69-112">Section index:</span></span>  <br/> |<span data-ttu-id="5fb69-113">**visSectionProp**</span><span class="sxs-lookup"><span data-stu-id="5fb69-113">**visSectionProp**</span></span> <br/> |
| <span data-ttu-id="5fb69-114">行索引：</span><span class="sxs-lookup"><span data-stu-id="5fb69-114">Row index:</span></span>  <br/> |<span data-ttu-id="5fb69-115">**visRowProp** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="5fb69-115">**visRowProp** +  *i*  where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="5fb69-116">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="5fb69-116">Cell index:</span></span>  <br/> |<span data-ttu-id="5fb69-117">**visCustPropsValue**</span><span class="sxs-lookup"><span data-stu-id="5fb69-117">**visCustPropsValue**</span></span> <br/> |
   

