---
title: LangID 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60048
localization_priority: Normal
ms.assetid: b6f5ea5e-b350-0817-d631-f059b9b95c23
description: 指示输入注释所使用的语言。
ms.openlocfilehash: 0de5ed8136a3fb1bbdca9fea0ebb5894e62cf907
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780524"
---
# <a name="langid-cell-annotation-section"></a>LangID 单元格（“Annotation”内容）

指示输入注释所使用的语言。
  
> [!NOTE]
> 此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。 它不用于跟踪.vsdx Visio 2013 中的文档中的注释。 
  
## <a name="remarks"></a>备注

此值是区域设置 ID (LCID) 的语言的输入注释所时语言栏上的活动。 Microsoft Office 应用程序所支持的语言的列表，请参阅[DocLangID](doclangid-cell-document-properties-section.md)单元格 （Document Properties 内容） 这一主题。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LangID 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Annotation.LangID [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionAnnotation** <br/> |
| 行索引：  <br/> |**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visAnnotationLangID** <br/> |
   

