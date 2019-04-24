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
ms.openlocfilehash: d9182932b8fa63c30473b93e420aa9efe30bf5eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346156"
---
# <a name="font-cell-character-section"></a>Font 单元格（“Character”内容）

代表用于设置文本格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。编号 0 代表默认的字体，通常为 Arial。
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Font 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char. Font [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 Font 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCharacterFont** <br/> |
   

