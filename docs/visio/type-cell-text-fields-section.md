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
ms.openlocfilehash: 68bfa8a84adb0d46d9621e6fc5383f4b6606f542
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781574"
---
# <a name="type-cell-text-fields-section"></a>Type 单元格（“Text Fields”内容）

指定文本域值的数据类型。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |字符串。  <br/> |
|2  <br/> |数字。包括日期、时间、持续时间和货币值，以及标量、尺寸和角度。在 Format 单元格中指定格式图片。  <br/> |
|5  <br/> |日期或时间值。显示日、月和年，或者秒、分钟和小时，或者日期和时间的组合值。在 Format 单元格中指定格式图片。  <br/> |
|6  <br/> |持续时间值。显示已经过去的时间。在 Format 单元格中指定格式图片。  <br/> |
|7  <br/> |货币值。使用系统的当前“区域设置”。在 Format 单元格中指定格式图片。  <br/> |
   
## <a name="remarks"></a>注解

您还可以设置此单元格，使用**字段**对话框中的值 （与选定形状，在**插入**选项卡中的**文本**组中，单击**域**）。 
  
若要获取对 Type 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Fields.Type [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Type 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionTextField** <br/> |
|行索引：  <br/> |**visRowField** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visFieldType** <br/> |
   

