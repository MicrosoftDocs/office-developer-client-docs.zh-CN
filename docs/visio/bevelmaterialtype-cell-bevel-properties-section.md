---
title: BevelMaterialType 单元格（“Bevel Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 30f50a94-88dc-41a3-bb46-45c92d6817a4
description: 确定的材料凹凸效果组成的类型。
ms.openlocfilehash: cd4ab223754ffcf7f46478cbc65faff373a3d692
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779705"
---
# <a name="bevelmaterialtype-cell-bevel-properties-section"></a>BevelMaterialType 单元格（“Bevel Properties”部分）

确定的材料凹凸效果组成的类型。 
  
|**说明**|**值**|
|:-----|:-----|
|0  <br/> |没有特殊的材料  <br/> |
|1  <br/> |亚光效果  <br/> |
|2  <br/> |暖色粗糙  <br/> |
|3  <br/> |塑料效果  <br/> |
|4  <br/> |金属效果  <br/> |
|5  <br/> |深边缘  <br/> |
|6  <br/> |柔边缘  <br/> |
|7  <br/> |平面  <br/> |
|8  <br/> |线框  <br/> |
|9  <br/> |粉  <br/> |
|10  <br/> |半透明粉  <br/> |
|11  <br/> |清除  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**BevelMaterialType**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BevelMaterialType  <br/> |
   
若要从某个程序按索引获取对**BevelMaterialType**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowBevelProperties** <br/> |
| 单元格索引：  <br/> |**visBevelMaterialType** <br/> |
   

