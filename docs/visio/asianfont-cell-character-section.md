---
title: AsianFont 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033764
localization_priority: Normal
ms.assetid: 45bfaaaa-52cc-f8b4-68e7-8b99e5788ce1
description: 包含用于设置含有亚洲字符的文字格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。
ms.openlocfilehash: 1fbaa0b27a0c639519c302129142dcefe5708115
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779647"
---
# <a name="asianfont-cell-character-section"></a>AsianFont 单元格（“Character”内容）

包含用于设置含有亚洲字符的文字格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。 
  
## <a name="remarks"></a>注解

**文本**对话框 （单击**主页**选项卡组的**字体**箭头） 中的**字体**选项卡上列出亚洲字体。 仅当您已添加了包含用于亚洲语言或复杂文种字符，在**Microsoft Office 语言首选项**对话框中的语言，将显示此列表。 （单击**开始**，单击**所有程序**，都单击**Microsoft Office**、 都单击**Microsoft Office 工具**，然后都单击**Microsoft Office 语言首选项**。
  
数字 0 表示未指定任何字体。如果西文字体或默认字体含有必需的字符，那么将使用这些字体。
  
若要获取对 AsianFont 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.AsianFont [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 AsianFont 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCharacterAsianFont** <br/> |
   

