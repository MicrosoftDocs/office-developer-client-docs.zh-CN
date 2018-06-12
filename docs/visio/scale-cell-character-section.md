---
title: Scale 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm870
localization_priority: Normal
ms.assetid: d6fe2574-b719-f38e-b1f1-592a812f1682
description: 控制字体宽度。该单元格的默认值是 100%。
ms.openlocfilehash: fedbc0aec23320d03ca358f34babda56eaab31e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781217"
---
# <a name="scale-cell-character-section"></a>Scale 单元格（“Character”内容）

控制字体宽度。该单元格的默认值是 100%。
  
## <a name="remarks"></a>注解

将百分比设置为介于 1% 和 99% 之间，可减少字体宽度。将百分比设置为介于 101% 和 600% 之间，可增加字体宽度。
  
您还可以使用**文本**对话框来设置此单元格的值 （在**主页**选项卡上，单击**字体**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Scale 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.FontScale [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Scale 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCharacterFontScale** <br/> |
   

