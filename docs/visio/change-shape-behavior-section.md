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
# <a name="change-shape-behavior-section"></a>"更改形状行为" 部分

确定在替换操作过程中从旧形状转移到替换形状的属性。 替换主控形状的 "**更改形状行为**" 部分中的单元格的值是在形状替换操作过程中读取的。 
  
## <a name="remarks"></a>注解

通过设置 "**更改形状行为**" 部分中的单元格, 可以确保替换形状的某些属性在替换操作过程中保持不变。 在操作过程中, 不受保护的属性将使用旧形状的本地形状值进行更新。 
  
您可以通过编辑主控形状来更改主控形状的替换行为设置 (在 "**形状**" 窗口中, 右键单击该形状, 指向 "**编辑主控**形状", 然后单击 "**编辑主控形状**"), 然后更改[](replacecopycells-cell-change-shape-behavior-section.md)主控形状 ShapeSheet 中的 ReplaceCopyCells、 [ReplaceLockFormat](replacelockformat-cell-change-shape-behavior-section.md)、 [ReplaceLockShapeData](replacelockshapedata-cell-change-shape-behavior-section.md)和[ReplaceLockText](replacelocktext-cell-change-shape-behavior-section.md)单元格。 
  
> [!NOTE]
> 您不能在 Microsoft Visio 2013 中更改内置模具附带的形状的形状替换行为。 若要修改内置 Visio 形状的形状替换行为, 请创建一个新模具, 并将您要修改的形状添加到新模具中。 
  

