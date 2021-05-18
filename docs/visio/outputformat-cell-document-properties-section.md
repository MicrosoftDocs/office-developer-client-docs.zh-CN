---
title: OutputFormat 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251617
localization_priority: Normal
ms.assetid: 17238019-c800-5d3a-32f6-fb0008d4e25f
description: 确定绘图的输出格式。绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。
ms.openlocfilehash: 09fa34095772936ab1c6a3025ed1884a533f55e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413883"
---
# <a name="outputformat-cell-document-properties-section"></a>OutputFormat 单元格（“Document Properties”内容）

确定绘图的输出格式。绘图页的格式通常是为打印而设置的（默认值）；不过您也可以选择其他输出格式。
  
|**值**|**输出格式**|
|:-----|:-----|
| 0  <br/> | 打印（默认值）  <br/> |
| 1  <br/> | PowerPoint 幻灯片放映  <br/> |
| 2  <br/> | HTML 或 GIF 输出  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 OutputFormat 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | OutputFormat  <br/> |
   
要从某个程序按索引获取对 OutputFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocOutputFormat** <br/> |
   

