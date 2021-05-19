---
title: "\"更改形状行为\"部分"
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a9e97f45-2a5c-40c3-8282-a345ae6249d9
description: 确定在替换操作过程中从旧形状转移到替换形状的属性。 替换的主控形状的"更改形状行为"部分中的单元格值在形状替换操作过程中读取。
ms.openlocfilehash: 74519b27ab5b2b5bafc7c00010a65769061bf691
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418664"
---
# <a name="change-shape-behavior-section"></a><span data-ttu-id="4cb6d-104">"更改形状行为"部分</span><span class="sxs-lookup"><span data-stu-id="4cb6d-104">Change Shape Behavior Section</span></span>

<span data-ttu-id="4cb6d-105">确定在替换操作过程中从旧形状转移到替换形状的属性。</span><span class="sxs-lookup"><span data-stu-id="4cb6d-105">Determines the properties that are transferred from the old shape to the replacement shape during a replacement operation.</span></span> <span data-ttu-id="4cb6d-106">替换的主控形状的"更改形状行为"部分中的单元格值在形状替换操作过程中读取。</span><span class="sxs-lookup"><span data-stu-id="4cb6d-106">The values of the cells in the **Change Shape Behavior** section of the Master shape of the replacement are read during the shape replacement operation.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="4cb6d-107">备注</span><span class="sxs-lookup"><span data-stu-id="4cb6d-107">Remarks</span></span>

<span data-ttu-id="4cb6d-108">通过设置"更改形状行为"部分中的单元格，可以确保替换形状的某些属性在替换操作过程中保持不变。</span><span class="sxs-lookup"><span data-stu-id="4cb6d-108">By setting the cells in the **Change Shape Behavior** section, you can ensure that certain properties of the replacement shape remain unchanged during the replacement operation.</span></span> <span data-ttu-id="4cb6d-109">在操作过程中，使用旧形状中的本地形状值更新未受保护的属性。</span><span class="sxs-lookup"><span data-stu-id="4cb6d-109">Properties that are not protected are updated with the local shape values from the old shape during the operation.</span></span> 
  
<span data-ttu-id="4cb6d-110">您可以通过在"形状"窗口中编辑主控形状 (、右键单击形状、指向"编辑主控形状"，然后单击"编辑主控形状形状) "并更改主控形状的 ShapeSheet 中的 ReplaceCopyCells、ReplaceLockFormat、ReplaceLockShapeData 和[ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md)单元格的值来更改主控形状的替换行为设置。 [](replacecopycells-cell-change-shape-behavior-section.md) [](replacelockformat-cell-change-shape-behavior-section.md) [](replacelockshapedata-cell-change-shape-behavior-section.md)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-110">You can change the replacement behavior settings of a Master shape by editing the Master shape (in the **Shapes** window, right-click the shape, point to **Edit Master**, and then click **Edit Master Shape**) and changing the values of the [ReplaceCopyCells](replacecopycells-cell-change-shape-behavior-section.md), [ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md), [ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md), and [ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md) cells in the Master's ShapeSheet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4cb6d-111">在 Microsoft 2013 中，无法更改内置模具中的形状Visio行为。</span><span class="sxs-lookup"><span data-stu-id="4cb6d-111">You cannot change the shape replacement behaviors of the shapes that are included with the built-in stencils in Microsoft Visio 2013.</span></span> <span data-ttu-id="4cb6d-112">若要修改内置模具的形状替换Visio，请新建一个模具，并添加要修改的形状。</span><span class="sxs-lookup"><span data-stu-id="4cb6d-112">To modify the shape replacement behaviors of the built-in Visio shapes, create a new stencil and add the shape that you want to modify to the new stencil.</span></span> 
  

