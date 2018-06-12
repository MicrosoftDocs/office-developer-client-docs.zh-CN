---
title: Strikethru 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm975
localization_priority: Normal
ms.assetid: b03b4415-0b1a-eb03-2b5e-373b39a0f07a
description: 确定文本格式是否设置为带删除线。
ms.openlocfilehash: 2b25d1d9b00d062214c02c3fc7b14569b43a5110
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781454"
---
# <a name="strikethru-cell-character-section"></a>Strikethru 单元格（“Character”内容）

确定文本格式是否设置为带删除线。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |将文本格式设为带删除线。  <br/> |
|FALSE  <br/> |将文本格式设为不带删除线。  <br/> |
   
## <a name="remarks"></a>注解

您还可以使用**文本**对话框来设置此单元格的值 （在**主页**选项卡上，单击**字体**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Strikethru 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.Strikethru [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Strikethru 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCharacterStrikethru** <br/> |
   

