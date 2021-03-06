---
title: Comment 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60033
localization_priority: Normal
ms.assetid: b367841a-f31c-4b55-4491-2abab5811dbe
description: 包含出现在注释中的文本。
ms.openlocfilehash: fd9dce2618c0b8c967b794b0beea8b772a231003
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415528"
---
# <a name="comment-cell-annotation-section"></a>Comment 单元格（“Annotation”内容）

包含出现在注释中的文本。
  
> [!NOTE]
> 此单元格仅用于在 Microsoft Visio 2013 中打开 .vsd 文件或以 .vsd 文件格式保存 .vsdx 文件时跟踪注释。 它不用于跟踪 2013 年 10 月 Visio中的注释。 
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Comment 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Annotation.Comment[  *i*  ] 其中  *i*  = <1>，2， 3...  <br/> |
   
要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionAnnotation** <br/> |
| 行索引：  <br/> |**visRowAnnotation**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visAnnotationComment** <br/> |
   

