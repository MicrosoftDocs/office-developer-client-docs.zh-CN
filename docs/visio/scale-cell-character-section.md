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
description: 控制字体宽度。 该单元格的默认值是 100%。
ms.openlocfilehash: 60e896772ddd1d59e1a1da7f2c0e90893658c624
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429150"
---
# <a name="scale-cell-character-section"></a>Scale 单元格（“Character”内容）

控制字体宽度。 该单元格的默认值是 100%。
  
## <a name="remarks"></a>说明

将百分比设置为介于 1% 和 99% 之间，可减少字体宽度。将百分比设置为介于 101% 和 600% 之间，可增加字体宽度。
  
还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上，单击 **“字体”** 箭头）设置此单元格的值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Scale 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |FontScale [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Scale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCharacterFontScale** <br/> |
   

