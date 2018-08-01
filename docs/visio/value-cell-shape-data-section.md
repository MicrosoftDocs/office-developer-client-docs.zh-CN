---
title: Value 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1090
localization_priority: Normal
ms.assetid: fd42a6ce-f621-4e9e-aba3-23a1b87a5651
description: 包含与在“定义形状数据”对话框中输入的形状数据项值相同的值。
ms.openlocfilehash: 5b373149360167585fc5a143ce9458703e219045
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781628"
---
# <a name="value-cell-shape-data-section"></a>Value 单元格（“Shape Data”部分）

包含与在 **“定义形状数据”** 对话框中输入的形状数据项值相同的值。 
  
## <a name="remarks"></a>说明

在 **“定义形状数据”** 对话框中输入的值将取代在此单元格中输入的公式。即使使用 GUARD 函数保护该公式，也同样会取代。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Value 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 属性。 *名称*。值其中属性。 *Name*是行名称  <br/> |
   
若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCustPropsValue** <br/> |
   

