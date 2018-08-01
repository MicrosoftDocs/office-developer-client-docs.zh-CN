---
title: User-defined Cells 行（“User-defined Cells”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm3060
localization_priority: Normal
ms.assetid: 6c48b9b3-5c62-7d5a-1c8f-fe96606f4dea
description: 包含解决方案中所有用户定义的单元格的值和说明性提示。对于每个用户定义的值/提示单元格对，形状都包含一个与之对应的 User-defined Cells 行。
ms.openlocfilehash: 45a9a033fe486a14e9881c3d79b79a129ecedc1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781600"
---
# <a name="user-defined-cells-row-user-defined-cells-section"></a><span data-ttu-id="d09e3-104">User-defined Cells 行（“User-defined Cells”部分）</span><span class="sxs-lookup"><span data-stu-id="d09e3-104">User-defined Cells Row (User-defined Cells Section)</span></span>

<span data-ttu-id="d09e3-p102">包含解决方案中所有用户定义的单元格的值和说明性提示。对于每个用户定义的值/提示单元格对，形状都包含一个与之对应的 User-defined Cells 行。</span><span class="sxs-lookup"><span data-stu-id="d09e3-p102">Contains the value and descriptive prompt for any user-defined cells in your solution. A shape contains one User-defined Cells row for each user-defined Value/Prompt cell pair.</span></span>
  
<span data-ttu-id="d09e3-107">用户定义的单元格行名用户。</span><span class="sxs-lookup"><span data-stu-id="d09e3-107">User-defined Cells rows are named User.</span></span> <span data-ttu-id="d09e3-108">*名称*，并且包含以下单元格。</span><span class="sxs-lookup"><span data-stu-id="d09e3-108">*name*  and contain the following cells.</span></span> <span data-ttu-id="d09e3-109">有关详细信息，请参阅特定单元格主题。</span><span class="sxs-lookup"><span data-stu-id="d09e3-109">For more details, see the specific cell topics.</span></span> 
  
|<span data-ttu-id="d09e3-110">**Cell**</span><span class="sxs-lookup"><span data-stu-id="d09e3-110">**Cell**</span></span>|<span data-ttu-id="d09e3-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="d09e3-111">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d09e3-112">Value</span><span class="sxs-lookup"><span data-stu-id="d09e3-112">Value</span></span>](value-cell-user-defined-cells-section.md) <br/> |<span data-ttu-id="d09e3-113">为相应的用户定义的单元格指定值。</span><span class="sxs-lookup"><span data-stu-id="d09e3-113">Specifies a value for the corresponding user-defined cell.</span></span>  <br/> |
|[<span data-ttu-id="d09e3-114">Prompt</span><span class="sxs-lookup"><span data-stu-id="d09e3-114">Prompt</span></span>](prompt-cell-user-defined-cells-section.md) <br/> |<span data-ttu-id="d09e3-115">为用户定义的单元格指定说明性提示或注释。</span><span class="sxs-lookup"><span data-stu-id="d09e3-115">Specifies a descriptive prompt or comment for the user-defined cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d09e3-116">注解</span><span class="sxs-lookup"><span data-stu-id="d09e3-116">Remarks</span></span>

<span data-ttu-id="d09e3-p104">用户定义的单元格可用于输入由其他单元格或加载项所引用的公式或常量。用户定义的单元格中的值是可移植的，也就是说，如果一个形状引用了某个形状中的用户定义的单元格，并且该形状被复制到另一个不含同一用户定义的单元格的形状中，则该单元格会被添加到另一个形状中。</span><span class="sxs-lookup"><span data-stu-id="d09e3-p104">User-defined cells can be used for entering formulas or constants that are referred to by other cells or add-ons. Values in user-defined cells are portable, that is, if a shape that refers to a user-defined cell in one shape is copied to another shape that does not have the same user-defined cell, the cell is added to the shape.</span></span>
  
 <span data-ttu-id="d09e3-119">您可以添加任意多个用户。</span><span class="sxs-lookup"><span data-stu-id="d09e3-119">You can add as many User.</span></span>  <span data-ttu-id="d09e3-120">*名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d09e3-120">*name*  rows as you need, assign meaningful names to the rows, and set cell values.</span></span> <span data-ttu-id="d09e3-121">要将行添加到现有的用户定义的单元格部分，右击某一行，然后单击快捷菜单上的**插入行**。</span><span class="sxs-lookup"><span data-stu-id="d09e3-121">To add a row to an existing User-defined Cells section, right-click a row and click **Insert Row** on the shortcut menu.</span></span> 
  
<span data-ttu-id="d09e3-122">可通过，这些行名称在 ShapeSheet 窗口中显示为红色文本来引用这些单元格。</span><span class="sxs-lookup"><span data-stu-id="d09e3-122">You can reference these cells by their row name, which appears in a ShapeSheet window in red text.</span></span> <span data-ttu-id="d09e3-123">为用户分配有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="d09e3-123">To assign meaningful names to User.</span></span> <span data-ttu-id="d09e3-124">*名称*行中，单击该行，，然后键入名称，例如*偏移*，例如，创建行名称指定有。</span><span class="sxs-lookup"><span data-stu-id="d09e3-124">*name*  rows, click the row, and then type a name such as  *Offset*  , for example, to create the row name User.Offset.</span></span> <span data-ttu-id="d09e3-125">然后，可以引用使用 User.Offset.Prompt Prompt 单元格。</span><span class="sxs-lookup"><span data-stu-id="d09e3-125">You can then reference the Prompt cell using User.Offset.Prompt.</span></span> 
  
<span data-ttu-id="d09e3-126">您输入的行名称在该内容中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d09e3-126">The row name you enter must be unique within the section.</span></span>
  

