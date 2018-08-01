---
title: UseGroupGradient 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f1dcf0ec-8b4a-4ee1-9208-b1c84e30d37b
description: 确定当形状以 Boolean 的形式进行分组以及其他形状时, 是否将形状承担渐变。 UseGroupGradient 单元格的值影响的形状填充。
ms.openlocfilehash: ca11ad1c54097b4883bb5348583c6cf39127e4e5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781605"
---
# <a name="usegroupgradient-cell-gradient-properties-section"></a>UseGroupGradient 单元格（“Gradient Properties”部分）

确定当形状以 Boolean 的形式进行分组以及其他形状时, 是否将形状承担渐变。 **UseGroupGradient**单元格的值影响的形状填充。 
  
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**UseGroupGradient**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | UseGroupGradient  <br/> |
   
若要从某个程序按索引获取对**UseGroupGradient**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |* * visUseGroupGradient * * <br/> |
   

