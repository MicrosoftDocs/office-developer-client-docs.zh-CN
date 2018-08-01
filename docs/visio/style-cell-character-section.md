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
ms.openlocfilehash: 48bda5eb798f439e2616b2b910d7ec5ac719d060
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781438"
---
# <a name="style-cell-character-section"></a>Style 单元格（“Character”部分）

显示应用于形状的文本块中一定范围内的文本的字符格式。
  
|**Style**|**值**|**自动常量**|
|:-----|:-----|:-----|
| 粗体  <br/> | &amp;H1  <br/> |**visBold** <br/> |
| 斜体  <br/> | &amp;H2  <br/> |**visItalic** <br/> |
| 下划线  <br/> | &amp;H4  <br/> |**visUnderLine** <br/> |
| 小型大写字母  <br/> | &amp;H8  <br/> |**visSmallCaps** <br/> |
   
## <a name="remarks"></a>注释

如果“Character”内容包含多行，则 Style 单元格包含应用于某形状文本的一个子范围的格式编排信息。否则，它就包含该形状的所有文本的格式设置信息。
  
值表示在其中的每个位表示字符样式二进制数。 例如，值为 3 代表倾斜和加粗格式的文本。 如果样式的值为 0，则文本是纯文本，或无格式。 您可以使用 Boolean 位某一特定格式测试\*函数。 请参阅编程文档有关这些函数的详细信息。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Style 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char.Style [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 Style 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCharacterStyle** <br/> |
   
 *示例* 
  
假设在某形状的“Character”内容的第一行中，Color 单元格设置为以下公式：
  
= IF(BITAND(Char.Style,1)=1,4,3)
  
那么，如果形状的文本的第一个字符是粗体，则第一个“Character”属性行所涵盖的文本将是蓝色 (4)；否则，它将是绿色 (3)。此示例假设默认颜色有效。
  
下面是一个在程序中设置 Style 单元格的例子。第一条语句按名称引用 Style 单元格，第二条语句按索引引用 Style 单元格。两条语句都在由形状的“Character”内容的第二行所涵盖的文本中应用斜体。
  

