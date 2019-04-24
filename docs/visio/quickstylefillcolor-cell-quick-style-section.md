---
title: QuickStyleFillColor 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 41250e47-404c-40e7-99be-9bb8c1ed5ba2
description: 确定形状的填充使用的主题颜色, 作为从0到7的整数
ms.openlocfilehash: 3ace0de7e3bfc878a2101eaca3847ef079b8f919
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358722"
---
# <a name="quickstylefillcolor-cell-quick-style-section"></a>QuickStyleFillColor 单元格 ("快速样式" 部分)

确定形状的填充使用的主题颜色, 作为从0到7的整数
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状填充颜色继承自 "深色" 主题颜色。  <br/> |
|1  <br/> |形状填充颜色继承自浅色主题颜色。  <br/> |
|双面  <br/> |形状填充颜色继承自 "强调文字颜色 1" 主题颜色  <br/> |
|第三章  <br/> |形状填充颜色继承自 "强调文字颜色 2" 主题颜色  <br/> |
|4  <br/> |形状填充颜色继承自 "强调文字颜色 3" 主题颜色  <br/> |
|5  <br/> |形状填充颜色继承自 "强调文字颜色 4" 主题颜色  <br/> |
|型  <br/> |形状填充颜色继承自 "强调文字颜色 5" 主题颜色  <br/> |
|步  <br/> |形状填充颜色继承自 "强调文字颜色 6" 主题颜色  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**QuickStyleFillColor**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleFillColor  <br/> |
   
若要从某个程序按索引获取对**QuickStyleFillColor**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleFillColor** <br/> |
   

