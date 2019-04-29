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
ms.openlocfilehash: b3b2cba3d0a04f75ef2d87f0ee8dcd1f8115e15e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422255"
---
# <a name="langid-cell-annotation-section"></a>LangID 单元格（“Annotation”内容）

指示输入注释所使用的语言。
  
> [!NOTE]
> 仅当在 Microsoft Visio 2013 中打开 .vsd 文件或以 .vsd 文件格式保存 .vsdx 文件时, 才会使用此单元格进行跟踪注释。 它不用于跟踪在 Visio 2013 中的 .vsdx 文档中的注释。 
  
## <a name="remarks"></a>说明

此值是输入注释时在语言栏上激活的语言的区域设置 ID (LCID)。有关 Microsoft Office 应用程序所支持的语言的列表，请参阅“[DocLangID](doclangid-cell-document-properties-section.md) 单元格（‘Document Properties’内容）”这一主题。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LangID 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LangID [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 LangID 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionAnnotation** <br/> |
| 行索引：  <br/> |**visRowAnnotation** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visAnnotationLangID** <br/> |
   

