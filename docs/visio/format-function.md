---
title: FORMAT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251424
localization_priority: Normal
ms.assetid: 52f5ef4d-07c6-ab36-bf74-b30b50eea221
description: 返回作为根据 formatpicture 设置格式的字符串表达式的结果。
ms.openlocfilehash: dcb898b3cb21d8cc5ebee7e56540d9e2eefcffdb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780313"
---
# <a name="format-function"></a>FORMAT 函数

根据_formatpicture_设置格式以字符串形式返回_表达式_的结果。
  
## <a name="syntax"></a>语法

格式 (* **表达式** *，"* * *formatpicture* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expression_ <br/> |必需  <br/> |**字符串** <br/> |常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。  <br/> |
| _formatpicture_ <br/> |必需  <br/> |**字符串** <br/> |用于设置字符串格式的格式图片。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>注解

表达式的类型和格式图片中指定的类型控制返回的字符串的行为。 _Formatpicture_必须适用于表达式的类型。 有关指定图片格式的详细信息，请参阅[关于设置图片格式](about-format-pictures.md)。
  
如果_expression_的结果和_formatpicture_中的类型不同类型的或在_formatpicture_中有语法错误，则返回错误。
  
## <a name="example-1"></a>示例 1

FORMAT(1cm/4, "0.000 u")
  
返回“0.250 cm”。
  
## <a name="example-2"></a>示例 2

FORMAT(1cm/4, "0.00 U")
  
返回“0.25 CM”。
  
## <a name="example-3"></a>示例 3

FORMAT(1cm/4, "0.0 u")
  
返回“0.3 cm”。
  

