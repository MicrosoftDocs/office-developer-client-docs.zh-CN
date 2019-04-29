---
title: BevelMaterialType 单元格 ("棱台属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 30f50a94-88dc-41a3-bb46-45c92d6817a4
description: 确定由斜角构成的材料的类型。
ms.openlocfilehash: b8efaa1f84594c803c79be02cd88dda1a5346dc7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414583"
---
# <a name="bevelmaterialtype-cell-bevel-properties-section"></a>BevelMaterialType 单元格 ("棱台属性" 部分)

确定由斜角构成的材料的类型。 
  
|**说明**|**值**|
|:-----|:-----|
|0  <br/> |无特殊材料  <br/> |
|1  <br/> |粗糙  <br/> |
|双面  <br/> |暖色粗糙  <br/> |
|第三章  <br/> |护  <br/> |
|4  <br/> |物  <br/> |
|5  <br/> |深色边缘  <br/> |
|型  <br/> |柔边缘  <br/> |
|步  <br/> |平面  <br/> |
|utf-8  <br/> |线框  <br/> |
|第  <br/> |浅  <br/> |
|10   <br/> |半透明粉  <br/> |
|11   <br/> |Clear  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**BevelMaterialType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BevelMaterialType  <br/> |
   
若要从某个程序按索引获取对**BevelMaterialType**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowBevelProperties** <br/> |
| 单元格索引：  <br/> |**visBevelMaterialType** <br/> |
   

