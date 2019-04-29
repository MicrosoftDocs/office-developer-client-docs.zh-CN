---
title: Prompt 单元格（“User-Defined Cells”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm840
localization_priority: Normal
ms.assetid: d0f91e7d-2373-cfef-e105-fb17e77c7f2d
description: 指定关于为用户定义的单元格的说明性提示或注释。 应用程序自动将提示文本括在引号 () 中, 以指示它是文本字符串。 如果键入等号 (=) 且省略引号，则可以在该单元格中输入应用程序求值的公式。
ms.openlocfilehash: 7684025e03bd3f4f68893179b1df00cc0cb535e2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435724"
---
# <a name="prompt-cell-user-defined-cells-section"></a>Prompt 单元格（“User-Defined Cells”内容）

指定关于为用户定义的单元格的说明性提示或注释。应用程序自动将提示文本用引号 (" ") 引起来，以表示它是文本字符串。如果键入等号 (=) 且省略引号，则可以在该单元格中输入应用程序求值的公式。
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Prompt 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | User.  *名称*。提示用户。  *名称*是行名称  <br/> |
   
要从某个程序按索引获取对 Prompt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionUser** <br/> |
| 行索引：  <br/> |**visRowUser +***i*其中*i* = 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visUserPrompt** <br/> |
   

