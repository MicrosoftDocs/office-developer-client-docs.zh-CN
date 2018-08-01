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
description: 为用户定义的单元格指定说明性提示或注释。 应用程序自动将提示文本括在双引号 （） 以指示它是一个文本字符串。 如果您键入一个等号 （=），并忽略引号，您可以在应用程序计算此单元格中输入公式。
ms.openlocfilehash: a7f8757af3e324a89f49bf5d19185b7a22173ff5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780995"
---
# <a name="prompt-cell-user-defined-cells-section"></a>Prompt 单元格（“User-Defined Cells”部分）

指定关于为用户定义的单元格的说明性提示或注释。应用程序自动将提示文本用引号 (" ") 引起来，以表示它是文本字符串。如果键入等号 (=) 且省略引号，则可以在该单元格中输入应用程序求值的公式。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Prompt 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 用户。  *名称*。提示位置用户。  *Name*是行名称  <br/> |
   
要从某个程序按索引获取对 Prompt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionUser** <br/> |
| 行索引：  <br/> |**visRowUser +***i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visUserPrompt** <br/> |
   

