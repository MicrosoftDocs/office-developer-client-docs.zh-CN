---
title: Value 单元格（“User-Defined Cells”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1100
localization_priority: Normal
ms.assetid: 495b2aec-e197-75eb-9974-e7c92d26546f
description: 为相应的用户定义的单元格指定值。
ms.openlocfilehash: d320c35fa8ae65dd0b21a83ad2cf23dbb3af77f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781623"
---
# <a name="value-cell-user-defined-cells-section"></a><span data-ttu-id="2ec0f-103">Value 单元格（“User-Defined Cells”部分）</span><span class="sxs-lookup"><span data-stu-id="2ec0f-103">Value Cell (User-Defined Cells Section)</span></span>

<span data-ttu-id="2ec0f-104">为相应的用户定义的单元格指定值。</span><span class="sxs-lookup"><span data-stu-id="2ec0f-104">Specifies a value for the corresponding user-defined cell.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2ec0f-105">注释</span><span class="sxs-lookup"><span data-stu-id="2ec0f-105">Remarks</span></span>

<span data-ttu-id="2ec0f-106">要在其他单元格中引用该值，请指定在行标签 User.Row 中输入的用户定义的名称。</span><span class="sxs-lookup"><span data-stu-id="2ec0f-106">To refer to this value in another cell, specify the user-defined name entered in the row label User.Row.</span></span>
  
<span data-ttu-id="2ec0f-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Value 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="2ec0f-107">To get a reference to the Value cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2ec0f-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="2ec0f-108">Cell name:</span></span>  <br/> | <span data-ttu-id="2ec0f-109">用户。</span><span class="sxs-lookup"><span data-stu-id="2ec0f-109">User.</span></span>  <span data-ttu-id="2ec0f-110">*名称*。值的位置用户。</span><span class="sxs-lookup"><span data-stu-id="2ec0f-110">*Name*  .Value            where User.</span></span>  <span data-ttu-id="2ec0f-111">*Name*是行名称</span><span class="sxs-lookup"><span data-stu-id="2ec0f-111">*Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="2ec0f-112">若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="2ec0f-112">To get a reference to the Value cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="2ec0f-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="2ec0f-113">Section index:</span></span>  <br/> |<span data-ttu-id="2ec0f-114">**visSectionUser**</span><span class="sxs-lookup"><span data-stu-id="2ec0f-114">**visSectionUser**</span></span> <br/> |
| <span data-ttu-id="2ec0f-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="2ec0f-115">Row index:</span></span>  <br/> |<span data-ttu-id="2ec0f-116">**visRowUser** +  *i*其中*i* = 0、 1、 2...</span><span class="sxs-lookup"><span data-stu-id="2ec0f-116">**visRowUser** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="2ec0f-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="2ec0f-117">Cell index:</span></span>  <br/> |<span data-ttu-id="2ec0f-118">**visUserValue**</span><span class="sxs-lookup"><span data-stu-id="2ec0f-118">**visUserValue**</span></span> <br/> |
   

