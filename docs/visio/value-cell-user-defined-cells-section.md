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
ms.openlocfilehash: 137d22430829f96a9c6ad69a73a6b44e964d5f4f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422986"
---
# <a name="value-cell-user-defined-cells-section"></a><span data-ttu-id="7b240-103">Value 单元格（“User-Defined Cells”内容）</span><span class="sxs-lookup"><span data-stu-id="7b240-103">Value Cell (User-Defined Cells Section)</span></span>

<span data-ttu-id="7b240-104">为相应的用户定义的单元格指定值。</span><span class="sxs-lookup"><span data-stu-id="7b240-104">Specifies a value for the corresponding user-defined cell.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7b240-105">备注</span><span class="sxs-lookup"><span data-stu-id="7b240-105">Remarks</span></span>

<span data-ttu-id="7b240-106">要在其他单元格中引用该值，请指定在行标签 User.Row 中输入的用户定义的名称。</span><span class="sxs-lookup"><span data-stu-id="7b240-106">To refer to this value in another cell, specify the user-defined name entered in the row label User.Row.</span></span>
  
<span data-ttu-id="7b240-107">要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Value 单元格的引用，请使用：</span><span class="sxs-lookup"><span data-stu-id="7b240-107">To get a reference to the Value cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7b240-108">单元格名称：</span><span class="sxs-lookup"><span data-stu-id="7b240-108">Cell name:</span></span>  <br/> | <span data-ttu-id="7b240-109">用户。</span><span class="sxs-lookup"><span data-stu-id="7b240-109">User.</span></span>  <span data-ttu-id="7b240-110">*名称*  。值，其中 User。</span><span class="sxs-lookup"><span data-stu-id="7b240-110">*Name*  .Value            where User.</span></span>  <span data-ttu-id="7b240-111">*Name*  是行名称</span><span class="sxs-lookup"><span data-stu-id="7b240-111">*Name*  is the row name</span></span>  <br/> |
   
<span data-ttu-id="7b240-112">要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性：</span><span class="sxs-lookup"><span data-stu-id="7b240-112">To get a reference to the Value cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="7b240-113">内容索引：</span><span class="sxs-lookup"><span data-stu-id="7b240-113">Section index:</span></span>  <br/> |<span data-ttu-id="7b240-114">**visSectionUser**</span><span class="sxs-lookup"><span data-stu-id="7b240-114">**visSectionUser**</span></span> <br/> |
| <span data-ttu-id="7b240-115">行索引：</span><span class="sxs-lookup"><span data-stu-id="7b240-115">Row index:</span></span>  <br/> |<span data-ttu-id="7b240-116">**visRowUser**  +  *i* 其中 *i* = 0、1、2...</span><span class="sxs-lookup"><span data-stu-id="7b240-116">**visRowUser** +  *i*            where  *i*  = 0, 1, 2...</span></span>  <br/> |
| <span data-ttu-id="7b240-117">单元格索引：</span><span class="sxs-lookup"><span data-stu-id="7b240-117">Cell index:</span></span>  <br/> |<span data-ttu-id="7b240-118">**visUserValue**</span><span class="sxs-lookup"><span data-stu-id="7b240-118">**visUserValue**</span></span> <br/> |
   

