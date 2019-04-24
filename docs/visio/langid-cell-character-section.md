---
title: LangID 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033769
localization_priority: Normal
ms.assetid: c68289b8-ef45-9e1e-12ae-6613587e4990
description: 指示输入文本所使用的语言。
ms.openlocfilehash: e1f244d6d8e31201576a9a88ace9701814b0e0a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326920"
---
# <a name="langid-cell-character-section"></a>LangID 单元格（“Character”内容）

指示输入文本所使用的语言。 
  
## <a name="remarks"></a>注解

有关 Microsoft Office 应用程序所支持的语言的列表，请参阅“[DocLangID](doclangid-cell-document-properties-section.md) 单元格（‘Document Properties’内容）”这一主题。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LangID [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCharacterLangID** <br/> |
   

