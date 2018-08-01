---
title: EVALCELL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4aa3a1c9-dec9-5eb0-5743-0534c0b3bb5f
description: 所需的引用的单元格包含自定义的函数，以及一个或多个要作为参数 （可选） 传递给自定义的函数的名称值对。 返回在给定所指定的参数和值的自定义函数的计算的结果。
ms.openlocfilehash: 03094f644edb29f990f3dda50b0cb4c35e1b07a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780188"
---
# <a name="evalcell-function"></a>EVALCELL 函数

所需的引用的单元格包含自定义的函数，以及一个或多个要作为参数 （可选） 传递给自定义的函数的名称值对。 返回在给定所指定的参数和值的自定义函数的计算的结果。
  
## <a name="syntax"></a>语法

EVALCELL (* * *cellRef* * *，[* * *arg1Name、 arg1* * *]，[* * *arg2Name、 arg2* * *]，...) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _cellRef_ <br/> |必需  <br/> |**字符串** <br/> |对包含自定义的函数的单元格的引用。 允许跨工作表引用。  <br/> |
| _arg1Name_ <br/> |可选  <br/> |**字符串** <br/> |要传递给自定义函数的第一个参数的名称。可以包含空格。  <br/> |
| _arg1_ <br/> |可选  <br/> |**因情况而异** <br/> |_Arg1_参数的值。  <br/> |
| _arg2Name_ <br/> |可选  <br/> |**字符串** <br/> |第二个参数传递给自定义的函数的名称。 允许使用空格。  <br/> |
| _arg2_ <br/> |可选  <br/> |**因情况而异** <br/> |_Arg2_参数的值。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>注解

调用单元格不必指定自定义函数使用的每一个参数。 
  
## <a name="example"></a>示例

以下示例显示了如何将 EVALCELL 函数与 ARG 函数一起使用，以查找一组三个值的中间值。 
  
在表达式单元格中，放置定义自定义函数的以下代码： 
  
```vb
User.MiddleValue = IF(ARG("A")>ARG("B"),IF(ARG("B")>ARG("C"),ARG("B"),IF(ARG("A")>ARG("C"),ARG("C"),ARG("A"))),IF(ARG("A")>ARG("C"),ARG("A"),IF(ARG("B")>ARG("C"),ARG("C"),ARG("B"))))
```

在调用单元格中，放置调用自定义函数的以下代码：
  
```vb
User.Middle1 = EVALCELL(User.MiddleValue,"A",3,"B",9,"C",5) 
User.Middle2 = EVALCELL(User.MiddleValue,"A",12,"B",0,"C",21) 

```


