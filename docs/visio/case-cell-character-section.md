---
title: Case 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251250
localization_priority: Normal
ms.assetid: cf063c05-5789-e037-700b-1e70df00e254
description: 确定形状文本的大小写。全部大写字母 (1) 和首字母大写字母 (2) 都不会更改以全部大写字母输入的文本的外观。只有文本是以小写字母输入时，这些选项才有效。
ms.openlocfilehash: 50ceaa1188caded40d36b8837c346fbbba2e14d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337231"
---
# <a name="case-cell-character-section"></a>Case 单元格（“Character”内容）

确定形状文本的大小写。全部大写字母 (1) 和首字母大写字母 (2) 都不会更改以全部大写字母输入的文本的外观。只有文本是以小写字母输入时，这些选项才有效。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 普通大小写  <br/> |**visCaseNormal** <br/> |
| 1  <br/> | 全部大写字母  <br/> |**visCaseAllCaps** <br/> |
| 双面  <br/> | 仅首字母大写字母  <br/> |**visCaseInitialCaps** <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Case 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char. [ *i* ] 其中*i* = <1>, 2, 3, .。。  <br/> |
   
要从某个程序按索引获取对 Case 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCharacterCase** <br/> |
   

