---
title: FORMATEX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251590
localization_priority: Normal
ms.assetid: d375c971-fee2-baa3-dc4f-a26018e70e8a
description: 格式以 dstUnit 表示根据格式表达式的结果计算 srcUnit 作为字符串返回。
ms.openlocfilehash: 08d123967272e0ab4e25990bcfab55cc80cef55d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780315"
---
# <a name="formatex-function"></a>FORMATEX 函数

格式以 dstUnit 表示根据格式表达式的结果计算 srcUnit 作为字符串返回。
  
## <a name="syntax"></a>语法

FORMATEX (* **表达式** *，"* **格式** *"，[* * *srcUnit* * *]，[* * *dstUnit* * *]，[* * *langID* * *] [，* * *calID* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**字符串** <br/> |常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。  <br/> |
| _format_ <br/> |必需  <br/> |**字符串** <br/> |用于设置格式的字符串格式的格式图片。 关于设置图片格式的详细信息，请参阅[有关格式图片](about-format-pictures.md)。  <br/> |
| _srcUnit_ <br/> |可选  <br/> |**字符串** <br/> | 用来计算 expression 的单位（in、cm 等）。  <br/> |
| _dstUnit_ <br/> |可选  <br/> |**字符串** <br/> |用于 expression 结果的单位（in、cm 等）。  <br/> |
| _langID_ <br/> |可选  <br/> |**编号** <br/> |设置 Microsoft Office System 日期/时间图片的格式时所使用的语言。  <br/> |
| _calID_ <br/> |可选  <br/> |**编号** <br/> |设置 Microsoft Office System 日期/时间图片的格式时所使用的日历。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>说明

表达式的类型和格式图片中指定的类型将控制返回的字符串的行为。format 必须适合该表达式的类型。
  
srcUnit 参数用于为非类型化的表达式的结果（如 3 + 4）提供单位。如果 expression 的结果具有显式类型，如 3 ft + 8 ft，则将忽略 srcUnit。
  
dstUnit 参数用于指定带格式的结果所使用的单位。如果未指定 dstUnit，则将使用表达式结果的单位。
  
在以下情况下将返回错误：expression 的结果和 format 中预期的类型不同；format 中出现语法错误；无法识别作为 srcUnit 或 dstUnit 传递的单位。
  
## <a name="example"></a>示例

FORMATEX(5.5, "0.00 u", "cm", "ft") 
  
返回 0.18 英尺。 
  

