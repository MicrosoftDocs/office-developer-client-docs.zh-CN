---
title: BevelBottomType 单元格 ("棱台属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ac7b39d4-3942-4b23-b188-2c3f69e54929
description: 指定形状棱台的底部棱台类型。
ms.openlocfilehash: 0cd360f633145c7dea95438ffe2bc746e519ce13
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330077"
---
# <a name="bevelbottomtype-cell-bevel-properties-section"></a>BevelBottomType 单元格 ("棱台属性" 部分)

指定形状棱台的底部棱台类型。
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |无棱台  <br/> |
|1  <br/> |圆形棱台  <br/> |
|双面  <br/> |松散内陷棱台  <br/> |
|第三章  <br/> |交叉棱台  <br/> |
|4  <br/> |酷斜面棱台  <br/> |
|5  <br/> |角斜面  <br/> |
|型  <br/> |柔圆棱台  <br/> |
|步  <br/> |凸棱台  <br/> |
|utf-8  <br/> |斜面棱台  <br/> |
|第  <br/> |草皮棱台  <br/> |
|10  <br/> |Riblet 棱台  <br/> |
|11x17  <br/> |硬边缘棱台  <br/> |
|12  <br/> |艺术装饰棱台  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**BevelBottomType**单元格的引用、按 .vsdx 文件格式的**cell**元素的**N**属性值或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BevelBottomType  <br/> |
   
若要从某个程序按索引获取对**BevelBottomType**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowBevelProperties** <br/> |
| 单元格索引：  <br/> |**visBevelBottomType** <br/> |
   

