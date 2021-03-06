---
title: Invisible 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251341
localization_priority: Normal
ms.assetid: 5f368c2e-2a40-38ee-3568-ed5c57633345
description: 指定形状数据项在“形状数据”窗口中是否可见。
ms.openlocfilehash: 8671fcc249b7ca81c011f697721093e7842c1558
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405315"
---
# <a name="invisible-cell-shape-data-section"></a>Invisible 单元格（“Shape Data”内容）

指定形状数据项在 **“形状数据”** 窗口中是否可见。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 形状数据项不可见。  <br/> |
| FALSE  <br/> | 形状数据项可见。  <br/> |
   
## <a name="remarks"></a>备注

此单元格中的值对应于 **“定义形状数据”** 对话框（右键单击形状，指向 **“数据”**，然后单击 **“定义形状数据”**）中的 **“隐藏”** 复选框。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Invisible 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Prop.  *name*  .在 Prop 中不可见。  *name*  是行名称  <br/> |
   
若要从某个程序按索引获取对 Invisible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visCustPropsInvis** <br/> |
   

