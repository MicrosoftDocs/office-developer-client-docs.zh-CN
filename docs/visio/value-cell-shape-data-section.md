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
description: 在定义形状数据对话框中输入包含形状数据项的值。
ms.openlocfilehash: 5b373149360167585fc5a143ce9458703e219045
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781628"
---
# <a name="value-cell-shape-data-section"></a>Value 单元格（“Shape Data”内容）

在**定义形状数据**对话框中输入包含形状数据项的值。 
  
## <a name="remarks"></a>备注

在**定义形状数据**对话框中输入值的情况下，输入此单元格中的公式所替代。 即使您使用 GUARD 函数保护公式，也是如此。 
  
若要获取对 Value 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 属性。 *名称*。值其中属性。 *Name*是行名称  <br/> |
   
若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCustPropsValue** <br/> |
   

