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
ms.openlocfilehash: 9acd786b6fa38aec42990f1fd942174367f1135e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779816"
---
# <a name="case-cell-character-section"></a>Case 单元格（“Character”部分）

确定形状文本的大小写。全部大写字母 (1) 和首字母大写字母 (2) 都不会更改以全部大写字母输入的文本的外观。只有文本是以小写字母输入时，这些选项才有效。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 普通大小写  <br/> |**visCaseNormal** <br/> |
| 1  <br/> | 全部大写字母  <br/> |**visCaseAllCaps** <br/> |
| 2  <br/> | 仅首字母大写字母  <br/> |**visCaseInitialCaps** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Case 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char.Case [ *i* ] 其中*i* = < 1 >，2，3，...  <br/> |
   
要从某个程序按索引获取对 Case 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCharacterCase** <br/> |
   

