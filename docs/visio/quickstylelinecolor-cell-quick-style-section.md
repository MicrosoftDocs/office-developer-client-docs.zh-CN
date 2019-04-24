---
title: QuickStyleLineColor 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: dcfb792f-e02a-4059-acec-a178d221097c
description: 确定形状的线条使用哪种主题颜色, 例如从0到7的整数。
ms.openlocfilehash: 010b943f2266b1e0ee192e5f1341d73851d176fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360045"
---
# <a name="quickstylelinecolor-cell-quick-style-section"></a>QuickStyleLineColor 单元格 ("快速样式" 部分)

确定形状的线条使用哪种主题颜色, 例如从0到7的整数。
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状线条颜色继承自深色主题颜色。  <br/> |
|1  <br/> |形状线条颜色继承自浅色主题颜色。  <br/> |
|双面  <br/> |形状线条颜色继承自 "强调文字颜色 1" 主题颜色  <br/> |
|第三章  <br/> |形状线条颜色继承自 "强调文字颜色 2" 主题颜色  <br/> |
|4  <br/> |形状线条颜色继承自 "强调文字颜色 3" 主题颜色  <br/> |
|5  <br/> |形状线条颜色继承自 "强调文字颜色 4" 主题颜色  <br/> |
|型  <br/> |形状线条颜色继承自 "强调文字颜色 5" 主题颜色  <br/> |
|步  <br/> |形状线条颜色继承自强调文字颜色6主题颜色  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**QuickStyleLineColor**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleLineColor  <br/> |
   
若要从某个程序按索引获取对**QuickStyleLineColor**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleLineColor** <br/> |
   

