---
title: ComplexScriptSize 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033768
localization_priority: Normal
ms.assetid: f58687d7-2ba4-ff77-0bcc-3106867d89de
description: 用于设置由复杂文种字符组成的文字的格式的字号。
ms.openlocfilehash: 38b01c4a0142c7eca2923ee9b13963eaa1a62830
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359341"
---
# <a name="complexscriptsize-cell-character-section"></a>ComplexScriptSize 单元格（“Character”内容）

用于设置由复杂文种字符组成的文字的格式的字号。 
  
## <a name="remarks"></a>注解

复杂文种字体大小在 "**文本**" 对话框 (单击 "**开始**" 选项卡上 "**字体**" 组中的箭头) 的 "**字体**" 选项卡上列出。 仅当您在**Microsoft Office 语言首选项**对话框中添加了包含亚洲或复杂脚本字符的语言时, 才会显示此列表。 (依次单击 "**开始**"、"**所有程序**"、" **microsoft office**"、" **microsoft office 工具**" 和 " **microsoft office 语言首选项**"。
  
您可以为此值输入明确的磅值或百分比。如果指定某一百分比，则该值将基于 Size 单元格中的值。默认值 0（零）表示 100%。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ComplexScriptSize 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ComplexScriptSize [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 ComplexScriptSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCharacterComplexScriptSize** <br/> |
   

