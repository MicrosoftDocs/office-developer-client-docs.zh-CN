---
title: Date 单元格（“Annotation”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60036
localization_priority: Normal
ms.assetid: f1f11803-614b-a40d-0a2d-131093e7609e
description: 包含最后编辑注释的日期和时间。
ms.openlocfilehash: 4b6e7ea70302b10728d82f36ad0db39077af9523
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780050"
---
# <a name="date-cell-annotation-section"></a>Date 单元格（“Annotation”部分）

包含最后编辑注释的日期和时间。 
  
> [!NOTE]
> 此单元格用于跟踪注释，仅当打开 Microsoft Visio 2013 中的.vsd 文件或.vsd 文件格式保存.vsdx 文件时。 它不用于跟踪.vsdx Visio 2013 中的文档中的注释。 
  
## <a name="remarks"></a>注释

该日期仅出现在用户界面的注释框中。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Date 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Annotation.Date [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 Date 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionAnnotation** <br/> |
| 行索引：  <br/> |**visRowAnnotation** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visAnnotationDate** <br/> |
   

