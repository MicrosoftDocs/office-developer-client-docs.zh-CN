---
title: Format 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251340
localization_priority: Normal
ms.assetid: c36fc895-5577-59f6-0ff5-5892ca81a58f
description: 指定形状数据项的格式，这些数据项是字符串、固定列表、数字、可变列表、日期或时间、持续时间或货币。
ms.openlocfilehash: bb02cfefd6dc93798ca5e2b0c657e4616515fd0e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346023"
---
# <a name="format-cell-shape-data-section"></a>Format 单元格（“Shape Data”内容）

指定形状数据项的格式，这些数据项是字符串、固定列表、数字、可变列表、日期或时间、持续时间或货币。
  
## <a name="remarks"></a>注解

|**形状数据项类型**|**值**|**Format 单元格内容**|
|:-----|:-----|:-----|
| 字符串  <br/> | 0  <br/> | 适合该数据类型的格式图片。  <br/> |
| 固定列表  <br/> | 1  <br/> | 要显示在列表中的项，以分号分隔。  <br/> |
| 帐号  <br/> | 双面  <br/> | 适合该数据类型的格式图片。  <br/> |
| 可变列表  <br/> | 4  <br/> | 要显示在列表中的项，以分号分隔。  <br/> |
| 日期或时间  <br/> | 5  <br/> | 适合该数据类型的格式图片。  <br/> |
| 持续时间  <br/> | 型  <br/> | 适合该数据类型的格式图片。  <br/> |
| 货币  <br/> | 步  <br/> | 适合该数据类型的格式图片。  <br/> |
   
以指定适合该数据类型的格式图片为例，格式图片“# #/4 UU”将数字 12.43 in. 设置为 12 2/4 INCHES 格式。有关指定格式图片的详细信息，请参见[关于格式图片](about-format-pictures.md)。
  
例如，将某个列表的各项指定为“Engineering;Human Resources;Sales;Marketing”。
  
日期值 (Type = 5) 以短日期格式显示。货币值 (Type = 7) 按用户在 **“控制面板”** 的 **“区域和语言选项”** 中 **“区域选项”** 选项卡上的 **“货币”** 的当前设置显示。
  
数字 (Type = 2) 可代表尺寸、标量、角度、日期、时间或货币。要确保始终将输入的数字作为日期、时间或货币计算，请在 Format 单元格中使用 DATETIME 或 CY 函数，而不是使用格式图片。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Format 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 片. *名称*。格式的格式。 *名称*是行名称  <br/> |
   
要从某个程序按索引获取对 Format 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCustPropsFormat** <br/> |
   

