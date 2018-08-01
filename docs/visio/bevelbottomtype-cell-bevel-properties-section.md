---
title: BevelBottomType 单元格（“Bevel Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ac7b39d4-3942-4b23-b188-2c3f69e54929
description: 指定形状的凹凸效果的底部凹凸效果类型。
ms.openlocfilehash: a0429011565d7a8f3ca0a7da76c08d309d5391f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779676"
---
# <a name="bevelbottomtype-cell-bevel-properties-section"></a>BevelBottomType 单元格（“Bevel Properties”部分）

指定形状的凹凸效果的底部凹凸效果类型。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |无棱台效果  <br/> |
|1  <br/> |Circle 凹凸效果  <br/> |
|2  <br/> |宽松的绘凹凸效果  <br/> |
|3  <br/> |Cross 凹凸效果  <br/> |
|4  <br/> |实用斜面凹凸效果  <br/> |
|5  <br/> |Angle 凹凸效果  <br/> |
|6  <br/> |柔圆凹凸效果  <br/> |
|7  <br/> |Convex 凹凸效果  <br/> |
|8  <br/> |Slope 凹凸效果  <br/> |
|9  <br/> |Divot 凹凸效果  <br/> |
|10  <br/> |Riblet 凹凸效果  <br/> |
|11  <br/> |硬边缘凹凸效果  <br/> |
|12  <br/> |艺术装饰凹凸效果  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** .vsdx 文件格式，**单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**BevelBottomType**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BevelBottomType  <br/> |
   
若要从某个程序按索引获取对**BevelBottomType**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowBevelProperties** <br/> |
| 单元格索引：  <br/> |**visBevelBottomType** <br/> |
   

