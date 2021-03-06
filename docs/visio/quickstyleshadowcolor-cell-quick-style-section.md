---
title: 'QuickStyleShadowColor Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0a80959f-941f-451c-9049-dc661ff4930f
description: 确定形状的阴影使用的主题颜色，作为从 0 到 7 的整数。
ms.openlocfilehash: b623eee89d214bade2706b12fcb344eccd8814b8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414954"
---
# <a name="quickstyleshadowcolor-cell-quick-style-section"></a>QuickStyleShadowColor Cell (Quick Style Section) 

确定形状的阴影使用的主题颜色，作为从 0 到 7 的整数。
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状阴影颜色继承自深色主题颜色。  <br/> |
|1  <br/> |形状阴影颜色继承自浅色主题颜色。  <br/> |
|2  <br/> |形状阴影颜色继承自强调文字颜色 1 主题颜色。  <br/> |
|3  <br/> |形状阴影颜色继承自强调文字颜色 2 主题颜色。  <br/> |
|4   <br/> |形状阴影颜色继承自强调文字颜色 3 主题颜色。  <br/> |
|5   <br/> |形状阴影颜色继承自强调文字颜色 4 主题颜色。  <br/> |
|6   <br/> |形状阴影颜色继承自强调文字颜色 5 主题颜色。  <br/> |
|7   <br/> |形状阴影颜色继承自强调文字颜色 6 主题颜色。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式、Cell 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **QuickStyleShadowColor** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleShadowColor  <br/> |
   
若要从程序按索引获取对 **QuickStyleShadowColor** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleShadowColor** <br/> |
   

