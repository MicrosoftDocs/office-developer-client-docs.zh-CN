---
title: Style 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251249
localization_priority: Normal
ms.assetid: 4372f1e1-f0a9-2f63-ff79-58f2afdceed5
description: 显示应用于形状的文本块中一定范围内的文本的字符格式。
ms.openlocfilehash: 349bdc42485aa511011aeb85a43f1ab3e4ea853d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411426"
---
# <a name="style-cell-character-section"></a>Style 单元格（“Character”内容）

显示应用于形状的文本块中一定范围内的文本的字符格式。
  
|**样式**|**值**|**自动常量**|
|:-----|:-----|:-----|
| 粗体  <br/> | &amp;H1  <br/> |**visBold** <br/> |
| 斜体  <br/> | &amp;H2  <br/> |**visItalic** <br/> |
| 下划线  <br/> | &amp;H4  <br/> |**visUnderLine** <br/> |
| 小型大写字母  <br/> | &amp;H8  <br/> |**visSmallCaps** <br/> |
   
## <a name="remarks"></a>说明

如果“Character”内容包含多行，则 Style 单元格包含应用于某形状文本的一个子范围的格式编排信息。否则，它就包含该形状的所有文本的格式设置信息。
  
该值表示二进制数字，其中每位代表均一种字符样式。 例如，值 3 表示格式既是斜体又是粗体的文本。 如果样式值为 0，则该文本是纯文本，即未设定任何格式。 您可以使用布尔位\*函数测试特定的格式。 有关这些函数的详细信息，请参考编程文档。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Style 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char. 样式 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 Style 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCharacterStyle** <br/> |
   
 *示例* 
  
假设在某形状的“Character”内容的第一行中，Color 单元格设置为以下公式：
  
= IF (BITAND (Char. Style, 1) = 1, 4, 3)
  
那么，如果形状的文本的第一个字符是粗体，则第一个“Character”属性行所涵盖的文本将是蓝色 (4)；否则，它将是绿色 (3)。此示例假设默认颜色有效。
  
下面是一个在程序中设置 Style 单元格的例子。第一条语句按名称引用 Style 单元格，第二条语句按索引引用 Style 单元格。两条语句都在由形状的“Character”内容的第二行所涵盖的文本中应用斜体。
  

