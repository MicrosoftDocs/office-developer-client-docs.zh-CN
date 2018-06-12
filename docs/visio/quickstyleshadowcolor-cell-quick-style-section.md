---
title: QuickStyleShadowColor 单元格 （快速样式内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0a80959f-941f-451c-9049-dc661ff4930f
description: 确定形状的阴影使用，为从 0 到 7 的整数的主题颜色。
ms.openlocfilehash: 303a1dfe44960920a6679ea4cc85fb849f8a9cba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781010"
---
# <a name="quickstyleshadowcolor-cell-quick-style-section"></a>QuickStyleShadowColor 单元格 （快速样式内容）

确定形状的阴影使用，为从 0 到 7 的整数的主题颜色。
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状阴影颜色继承自深主题颜色。  <br/> |
|1  <br/> |形状阴影颜色继承自浅主题颜色。  <br/> |
|2  <br/> |形状阴影颜色继承自强调文字颜色 1 主题颜色。  <br/> |
|3  <br/> |形状阴影颜色继承自强调文字颜色 2 主题颜色。  <br/> |
|4  <br/> |形状阴影颜色继承自强调文字颜色 3 主题颜色。  <br/> |
|5  <br/> |形状阴影颜色继承自强调文字颜色 4 主题颜色。  <br/> |
|6  <br/> |形状阴影颜色继承自强调文字颜色 5 主题颜色。  <br/> |
|7  <br/> |形状阴影颜色继承自强调文字颜色 6 主题颜色。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**QuickStyleShadowColor**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleShadowColor  <br/> |
   
若要从某个程序按索引获取对**QuickStyleShadowColor**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleShadowColor** <br/> |
   

