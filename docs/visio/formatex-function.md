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
description: 返回在 srcUnit 中根据 dstUnit 表示的格式格式化的字符串计算表达式的结果。
ms.openlocfilehash: e341cbcb16cc273f0413f98c195f77ad08946ab1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430964"
---
# <a name="formatex-function"></a>FORMATEX 函数

返回在 srcUnit 中根据 dstUnit 表示的格式格式化的字符串计算表达式的结果。
  
## <a name="syntax"></a>语法

FORMATEX (** *expression* **，" ** *format* ** "，[ ** *srcUnit* ** ]，[ ** *dstUnit* ** ]，[ ** *langID* ** ][， ** *calID* ** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**String** <br/> |常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。  <br/> |
| _format_ <br/> |必需  <br/> |**String** <br/> |用于设置字符串格式的格式图片。 有关设置图片格式的信息，请参阅关于 [设置图片格式](about-format-pictures.md)。  <br/> |
| _srcUnit_ <br/> |可选  <br/> |**字符串** <br/> | 用来计算 expression 的单位（in、cm 等）。  <br/> |
| _dstUnit_ <br/> |可选  <br/> |**字符串** <br/> |用于 expression 结果的单位（in、cm 等）。  <br/> |
| _langID_ <br/> |可选  <br/> |**Number** <br/> |设置 Microsoft Office System 日期/时间图片的格式时所使用的语言。  <br/> |
| _calID_ <br/> |可选  <br/> |**Number** <br/> |设置 Microsoft Office System 日期/时间图片的格式时所使用的日历。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>备注

表达式的类型和格式图片中指定的类型将控制返回的字符串的行为。format 必须适合该表达式的类型。
  
srcUnit 参数用于为非类型化的表达式的结果（如 3 + 4）提供单位。如果 expression 的结果具有显式类型，如 3 ft + 8 ft，则将忽略 srcUnit。
  
dstUnit 参数用于指定带格式的结果所使用的单位。如果未指定 dstUnit，则将使用表达式结果的单位。
  
在以下情况下将返回错误：expression 的结果和 format 中预期的类型不同；format 中出现语法错误；无法识别作为 srcUnit 或 dstUnit 传递的单位。
  
## <a name="example"></a>示例

FORMATEX(5.5, "0.00 u", "cm", "ft") 
  
返回 0.18 英尺。 
  

