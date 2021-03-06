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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428436"
---
# <a name="complexscriptsize-cell-character-section"></a>ComplexScriptSize 单元格（“Character”内容）

用于设置由复杂文种字符组成的文字的格式的字号。 
  
## <a name="remarks"></a>备注

复杂脚本字体大小列在"文本"对话框的"字体"选项卡上 (单击"开始"选项卡上"字体"组中) 。   只有在"语言首选项"对话框中添加了包含亚洲语言或复杂脚本字符 **Microsoft Office，** 此列表才显示。  (**单击开始**，单击所有 **程序，Microsoft Office，** 单击Microsoft Office **工具**，然后单击Microsoft Office **语言首选项。**
  
您可以为此值输入明确的磅值或百分比。如果指定某一百分比，则该值将基于 Size 单元格中的值。默认值 0（零）表示 100%。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ComplexScriptSize 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.ComplexScriptSize[ *i*  ] 其中  *i*  = <1> 2， 3...  <br/> |
   
若要从某个程序按索引获取对 ComplexScriptSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter**  +  *i* 其中 *i* = 0、1、2...  <br/> |
|单元格索引：  <br/> |**visCharacterComplexScriptSize** <br/> |
   

