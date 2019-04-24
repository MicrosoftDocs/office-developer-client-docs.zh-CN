---
title: QuickStyleFillMatrix 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8513cf3f-42bd-4e76-bfa8-8bf12f0d1296
description: 确定形状继承自活动主题的快速样式填充样式 (从0-6 的整数)。
ms.openlocfilehash: fca0d9f8fe58fdc7c227e9c093b418ffef1ccb52
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358714"
---
# <a name="quickstylefillmatrix-cell-quick-style-section"></a>QuickStyleFillMatrix 单元格 ("快速样式" 部分)

确定形状继承自活动主题的快速样式填充样式 (从0-6 的整数)。 
  
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**QuickStyleFillMatrix**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleFillMatrix  <br/> |
   
若要从某个程序按索引获取对**QuickStyleFillMatrix**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleFillMatrix** <br/> |
   

