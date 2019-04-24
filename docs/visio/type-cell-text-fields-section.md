---
title: Type 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1060
localization_priority: Normal
ms.assetid: 69d64520-9a47-07ca-09c7-d1e5da620348
description: 指定文本域值的数据类型。
ms.openlocfilehash: 91a2d60133d9a39e152656558f168742a5409883
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358924"
---
# <a name="type-cell-text-fields-section"></a>Type 单元格（“Text Fields”内容）

指定文本域值的数据类型。
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |字符串。  <br/> |
|双面  <br/> |数字。包括日期、时间、持续时间和货币值，以及标量、尺寸和角度。在 Format 单元格中指定格式图片。  <br/> |
|5  <br/> |日期或时间值。显示日、月和年，或者秒、分钟和小时，或者日期和时间的组合值。在 Format 单元格中指定格式图片。  <br/> |
|型  <br/> |持续时间值。显示已经过去的时间。在 Format 单元格中指定格式图片。  <br/> |
|步  <br/> |货币值。使用系统的当前“区域设置”。在 Format 单元格中指定格式图片。  <br/> |
   
## <a name="remarks"></a>注解

您还可以使用 "**域**" 对话框 (在选定形状的情况下, 在 "**插入**" 选项卡上的 "**文本**" 组中, 单击 "**域**") 设置此单元格的值。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Type 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Fields。键入 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Type 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionTextField** <br/> |
|行索引：  <br/> |**visRowField** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visFieldType** <br/> |
   

