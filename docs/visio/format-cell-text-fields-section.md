---
title: Format 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm400
localization_priority: Normal
ms.assetid: ab937a00-84c2-6c1c-9080-b7c95ead4f63
description: 指定文本域的格式，该文本字段可以是字符串、数字、日期或时间、持续时间或货币。
ms.openlocfilehash: 767b658a9431dfab23d2df9bcfa6c83b52f48d75
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780310"
---
# <a name="format-cell-text-fields-section"></a>Format 单元格（“Text Fields”部分）

指定文本域的格式，该文本字段可以是字符串、数字、日期或时间、持续时间或货币。
  
## <a name="remarks"></a>注解

如果 Type 单元格的值为 0、2、5、6 或 7（分别代表字符串、数字、日期或时间、持续时间或货币），请为该数据类型指定适当的格式图片。例如，格式图片“# #/4 UU”将数字 12.43 in. 设置为 12 2/4 INCHES 格式。有关指定格式图片的详细信息，请参见[关于格式图片](about-format-pictures.md)。
  
数字 (Type = 2) 可代表尺寸、标量、角度、日期、时间或货币。要确保始终将输入的数字作为日期、时间或货币计算，请在 Format 单元格中使用 DATETIME 或 CY 函数，而不是使用格式图片。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Format 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Fields.Format [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 Format 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTextField** <br/> |
| 行索引：  <br/> |**visRowField** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visFieldFormat** <br/> |
   

