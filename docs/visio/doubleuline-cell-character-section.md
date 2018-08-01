---
title: DoubleULine 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm260
localization_priority: Normal
ms.assetid: c18955c8-d653-c29d-d3da-9d3cd0241e17
description: 确定文本范围下是否带有双下划线。
ms.openlocfilehash: d0a07d8c86bd7e9ed3eb14074dda164f82c92475
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780146"
---
# <a name="doubleuline-cell-character-section"></a>DoubleULine 单元格（“Character”部分）

确定文本范围下是否带有双下划线。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |文本下带有双下划线。  <br/> |
|FALSE  <br/> |文本下不带双下划线。  <br/> |
   
## <a name="remarks"></a>注解

如果“Characters”内容包含多行，则 DoubleULine 单元格包含应用于某形状文本的一个子范围的格式设置信息。否则，它就包含该形状的所有文本的格式设置信息。
  
还可以使用 **“文本”** 对话框（在 **“开始”** 选项卡上单击 **“字体”**）设置此单元格的值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DoubleULine 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.DblUnderline [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 DoubleULine 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCharacterDblUnderline** <br/> |
   

