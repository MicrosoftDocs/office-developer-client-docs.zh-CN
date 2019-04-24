---
title: "\"更改形状行为\" 部分"
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a9e97f45-2a5c-40c3-8282-a345ae6249d9
description: 确定在替换操作过程中从旧形状转移到替换形状的属性。 替换主控形状的 "更改形状行为" 部分中的单元格的值是在形状替换操作过程中读取的。
ms.openlocfilehash: 74519b27ab5b2b5bafc7c00010a65769061bf691
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341921"
---
# <a name="change-shape-behavior-section"></a><span data-ttu-id="c3d11-104">"更改形状行为" 部分</span><span class="sxs-lookup"><span data-stu-id="c3d11-104">Change Shape Behavior Section</span></span>

<span data-ttu-id="c3d11-105">确定在替换操作过程中从旧形状转移到替换形状的属性。</span><span class="sxs-lookup"><span data-stu-id="c3d11-105">Determines the properties that are transferred from the old shape to the replacement shape during a replacement operation.</span></span> <span data-ttu-id="c3d11-106">替换主控形状的 "**更改形状行为**" 部分中的单元格的值是在形状替换操作过程中读取的。</span><span class="sxs-lookup"><span data-stu-id="c3d11-106">The values of the cells in the **Change Shape Behavior** section of the Master shape of the replacement are read during the shape replacement operation.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c3d11-107">注解</span><span class="sxs-lookup"><span data-stu-id="c3d11-107">Remarks</span></span>

<span data-ttu-id="c3d11-108">通过设置 "**更改形状行为**" 部分中的单元格, 可以确保替换形状的某些属性在替换操作过程中保持不变。</span><span class="sxs-lookup"><span data-stu-id="c3d11-108">By setting the cells in the **Change Shape Behavior** section, you can ensure that certain properties of the replacement shape remain unchanged during the replacement operation.</span></span> <span data-ttu-id="c3d11-109">在操作过程中, 不受保护的属性将使用旧形状的本地形状值进行更新。</span><span class="sxs-lookup"><span data-stu-id="c3d11-109">Properties that are not protected are updated with the local shape values from the old shape during the operation.</span></span> 
  
<span data-ttu-id="c3d11-110">您可以通过编辑主控形状来更改主控形状的替换行为设置 (在 "**形状**" 窗口中, 右键单击该形状, 指向 "**编辑主控**形状", 然后单击 "**编辑主控形状**"), 然后更改[](replacecopycells-cell-change-shape-behavior-section.md)主控形状 ShapeSheet 中的 ReplaceCopyCells、 [ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md)、 [ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md)和[ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md)单元格。</span><span class="sxs-lookup"><span data-stu-id="c3d11-110">You can change the replacement behavior settings of a Master shape by editing the Master shape (in the **Shapes** window, right-click the shape, point to **Edit Master**, and then click **Edit Master Shape**) and changing the values of the [ReplaceCopyCells](replacecopycells-cell-change-shape-behavior-section.md), [ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md), [ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md), and [ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md) cells in the Master's ShapeSheet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c3d11-111">您不能在 Microsoft Visio 2013 中更改内置模具附带的形状的形状替换行为。</span><span class="sxs-lookup"><span data-stu-id="c3d11-111">You cannot change the shape replacement behaviors of the shapes that are included with the built-in stencils in Microsoft Visio 2013.</span></span> <span data-ttu-id="c3d11-112">若要修改内置 Visio 形状的形状替换行为, 请创建一个新模具, 并将您要修改的形状添加到新模具中。</span><span class="sxs-lookup"><span data-stu-id="c3d11-112">To modify the shape replacement behaviors of the built-in Visio shapes, create a new stencil and add the shape that you want to modify to the new stencil.</span></span> 
  

