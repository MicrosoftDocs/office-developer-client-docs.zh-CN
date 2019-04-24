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
ms.openlocfilehash: 4af7e590a7bd0733ad622f3df259aa6c01837c4b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341327"
---
# <a name="asianfont-cell-character-section"></a>AsianFont 单元格（“Character”内容）

包含用于设置含有亚洲字符的文字格式的字体编号。根据您的系统上安装的字体，字体编号会有所不同。 
  
## <a name="remarks"></a>注解

亚洲字体在 **“文本”** 对话框中的 **“字体”** 选项卡（单击 **“开始”** 选项卡上的 **“字体”** 组中的箭头）上列出。只有在 **“Microsoft Office 语言首选项”** 对话框（依次单击 **“开始”**、**“所有程序”**、**“Microsoft Office”**、**“Microsoft Office 工具”** 和 **“Microsoft Office 语言首选项”**）中添加了包含亚洲或复杂文种字符的语言后，才会显示此列表。
  
数字 0 表示未指定任何字体。如果西文字体或默认字体含有必需的字符，那么将使用这些字体。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AsianFont 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |AsianFont [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 AsianFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCharacterAsianFont** <br/> |
   

