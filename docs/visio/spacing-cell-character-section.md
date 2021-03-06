---
title: Spacing 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm955
localization_priority: Normal
ms.assetid: 46feb136-01ac-1303-66ab-d772c0ec41a0
description: 控制两个或多个字符之间的空间量。空间量可以二十分之一磅为增量增加或减少。
ms.openlocfilehash: 927b6203b81af453411cdd13b6f8c8342507a61b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430061"
---
# <a name="spacing-cell-character-section"></a>Spacing 单元格（“Character”内容）

控制两个或多个字符之间的空间量。空间量可以二十分之一磅为增量增加或减少。
  
## <a name="remarks"></a>备注

还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）设置此单元格的值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Spacing 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.Letterspace[ *i*  ] 其中  *i*  = <1> 2， 3...  <br/> |
   
若要从某个程序按索引获取对 Spacing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter**  +  *i* 其中 *i* = 0、1、2...  <br/> |
|单元格索引：  <br/> |**visCharacterLetterspace** <br/> |
   

