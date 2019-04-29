---
title: ComplexScriptFont 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60034
localization_priority: Normal
ms.assetid: e1cf9e97-101b-384f-65fe-0169c89dfccc
description: 包含用于设置由复杂文种字符组成的文字的格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。
ms.openlocfilehash: 5ec8deb59b875a01592b6d7b652204089ecf11e0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404832"
---
# <a name="complexscriptfont-cell-character-section"></a>ComplexScriptFont 单元格（“Character”内容）

包含用于设置由复杂文种字符组成的文字的格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。 
  
## <a name="remarks"></a>说明

复杂文种字体大小在 "**文本**" 对话框 (单击 "**开始**" 选项卡上 "**字体**" 组中的箭头) 的 "**字体**" 选项卡上列出。 仅当您在**Microsoft Office 语言首选项**对话框中添加了包含亚洲或复杂脚本字符的语言时, 才会显示此列表。 (依次单击 "**开始**"、"**所有程序**"、" **microsoft office**"、" **microsoft office 工具**" 和 " **microsoft office 语言首选项**"。
  
数字 0（零）表示未指定任何字体。 将使用西文字体或默认字体。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ComplexScriptSize 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ComplexScriptFont [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 ComplexScriptFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCharacterComplexScriptFont** <br/> |
   

