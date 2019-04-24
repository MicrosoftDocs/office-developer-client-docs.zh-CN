---
title: Overline 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251728
localization_priority: Normal
ms.assetid: 102cce17-43ee-e313-3412-a72d6ee18fe6
description: 确定在文本之上是否存在线条。
ms.openlocfilehash: d5df39c2f12890d5fb4881346516abdb4f2b8099
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327046"
---
# <a name="overline-cell-character-section"></a>Overline 单元格（“Character”内容）

确定在文本之上是否存在线条。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |文本之上存在线条。  <br/> |
|FALSE  <br/> |文本之上没有线条。  <br/> |
   
## <a name="remarks"></a>注解

还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）设置此单元格的值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Overline 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char. 上划线 [ *i* ] 其中*i* = <1>, 2。 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Overline 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCharacterOverline** <br/> |
   

