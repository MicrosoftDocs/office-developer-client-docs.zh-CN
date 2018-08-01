---
title: “Change Shape Behavior”部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a9e97f45-2a5c-40c3-8282-a345ae6249d9
description: 决定转给从旧的形状的替换形状替换操作期间的属性。 值替换为相应的形状读取形状替换操作期间的主控形状更改形状行为部分中的单元格。
ms.openlocfilehash: 3b4b3cac37b8415309a2433c19c2b420fd652df7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779853"
---
# <a name="change-shape-behavior-section"></a><span data-ttu-id="63122-104">“Change Shape Behavior”部分</span><span class="sxs-lookup"><span data-stu-id="63122-104">Change Shape Behavior Section</span></span>

<span data-ttu-id="63122-105">决定转给从旧的形状的替换形状替换操作期间的属性。</span><span class="sxs-lookup"><span data-stu-id="63122-105">Determines the properties that are transferred from the old shape to the replacement shape during a replacement operation.</span></span> <span data-ttu-id="63122-106">值替换为相应的形状读取形状替换操作期间的主控形状**更改形状行为**部分中的单元格。</span><span class="sxs-lookup"><span data-stu-id="63122-106">The values of the cells in the **Change Shape Behavior** section of the Master shape of the replacement are read during the shape replacement operation.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="63122-107">说明</span><span class="sxs-lookup"><span data-stu-id="63122-107">Remarks</span></span>

<span data-ttu-id="63122-108">通过在**更改形状行为**部分中设置单元格，您可以确保替换操作期间的替换形状的某些属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="63122-108">By setting the cells in the **Change Shape Behavior** section, you can ensure that certain properties of the replacement shape remain unchanged during the replacement operation.</span></span> <span data-ttu-id="63122-109">在操作过程中，从旧的形状的本地形状值更新不受保护的属性。</span><span class="sxs-lookup"><span data-stu-id="63122-109">Properties that are not protected are updated with the local shape values from the old shape during the operation.</span></span> 
  
<span data-ttu-id="63122-110">您可以更改替换为通过编辑主控形状的主控形状的行为设置形状 （在**形状**窗口中，右键单击形状，指向**编辑主控形状**，然后单击**编辑主控形状**） 和更改[的值ReplaceCopyCells](replacecopycells-cell-change-shape-behavior-section.md)， [ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md)、 [ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md)和[ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md)主控形状的 ShapeSheet 中的单元格。</span><span class="sxs-lookup"><span data-stu-id="63122-110">You can change the replacement behavior settings of a Master shape by editing the Master shape (in the **Shapes** window, right-click the shape, point to **Edit Master**, and then click **Edit Master Shape**) and changing the values of the [ReplaceCopyCells](replacecopycells-cell-change-shape-behavior-section.md), [ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md), [ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md), and [ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md) cells in the Master's ShapeSheet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="63122-111">不能更改 Microsoft Visio 2013 中的内置模具中包含的形状的形状替换行为。</span><span class="sxs-lookup"><span data-stu-id="63122-111">You cannot change the shape replacement behaviors of the shapes that are included with the built-in stencils in Microsoft Visio 2013.</span></span> <span data-ttu-id="63122-112">若要修改内置 Visio 形状的形状替换行为，创建的新模具，并添加您想要修改的新模具的形状。</span><span class="sxs-lookup"><span data-stu-id="63122-112">To modify the shape replacement behaviors of the built-in Visio shapes, create a new stencil and add the shape that you want to modify to the new stencil.</span></span> 
  

