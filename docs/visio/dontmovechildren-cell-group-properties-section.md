---
title: DontMoveChildren 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm255
localization_priority: Normal
ms.assetid: ff5bbf05-4851-30ce-7ee1-f0ce7b2781ab
description: 确定是否可以使用鼠标拖动组合中的形状。
ms.openlocfilehash: 2b15d75a98b5f5a72bce8b80758d27b197a346ed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416592"
---
# <a name="dontmovechildren-cell-group-properties-section"></a>DontMoveChildren 单元格（“Group Properties”内容）

确定是否可以使用鼠标拖动组合中的形状。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不允许使用鼠标拖动组合中的形状。  <br/> |
| FALSE  <br/> | 允许使用鼠标拖动组合中的形状。  <br/> |
   
## <a name="remarks"></a>备注

如果该单元格的值为 TRUE，您还可以使用其他方法翻转、旋转或重定位组合中的形状，或者更改这些形状的大小。
  
对于主控形状中的组合以及在低于 Visio 2000 的版本中创建的主控形状实例中的组合，该单元格的值为 TRUE。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DontMoveChildren 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DontMoveChildren  <br/> |
   
要从某个程序按索引获取对 DontMoveChildren 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGroup** <br/> |
| 单元格索引：  <br/> |**visGroupDontMoveChildren** <br/> |
   

