---
title: LangID 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033771
localization_priority: Normal
ms.assetid: 6bd2781a-d4e7-136f-8996-62ebc5f890ab
description: 指示输入形状数据值所使用的语言。
ms.openlocfilehash: c5a0cca5f71bc5520337ad2bdcf354a2b4affe92
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359029"
---
# <a name="langid-cell-shape-data-section"></a>LangID 单元格（“Shape Data”内容）

指示输入形状数据值所使用的语言。 
  
## <a name="remarks"></a>注解

有关 Microsoft Office 系统应用程序所支持的语言的列表，请参阅 [DocLangID](doclangid-cell-document-properties-section.md) 单元格（“Document Properties”内容）。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LangID 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 片. *名称*。LangID 其中的一个。 *名称*是行名称  <br/> |
   
若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCustPropsLangID** <br/> |
   

