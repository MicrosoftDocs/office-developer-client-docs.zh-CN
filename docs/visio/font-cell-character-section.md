---
title: Font 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm390
localization_priority: Normal
ms.assetid: 935760a9-307e-90bc-c301-d04283d97427
description: 代表用于设置文本格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。编号 0 代表默认的字体，通常为 Arial。
ms.openlocfilehash: cbbf2a2400c995e0cbc217c1161fbd18f7459b28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780279"
---
# <a name="font-cell-character-section"></a>Font 单元格（“Character”内容）

代表用于设置文本格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。编号 0 代表默认的字体，通常为 Arial。
  
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Font 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char.Font [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Font 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCharacterFont** <br/> |
   

