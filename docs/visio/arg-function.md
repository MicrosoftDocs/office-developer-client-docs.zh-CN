---
title: ARG 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 781369e1-fade-ec10-7c51-0f921b5c3b76
description: 指定调用单元格可以传递到自定义函数的参数，以及当调用单元格未传递该参数的值时自定义函数返回的默认值。返回调用单元格指定的值以及匹配的 argName 参数。
ms.openlocfilehash: 3cde7fe55d7bc60d15f32d7ad954443e545af914
ms.sourcegitcommit: 939bd9686ba41a8f94b82e004ed84b9054d9c7cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48293483"
---
# <a name="arg-function"></a>ARG 函数

指定调用单元格可以传递到自定义函数的参数，以及当调用单元格未传递该参数的值时自定义函数返回的默认值。返回调用单元格指定的值以及匹配的 argName 参数。
  
## <a name="syntax"></a>语法

ARG (***argName***，[ ***defaultValue*** ])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _argName_ <br/> |必需  <br/> |**String** <br/> |调用单元格可以传递给该函数的参数的名称。  <br/> |
| _默认值_ <br/> |可选  <br/> |**Numeric** <br/> |如果调用单元格未传递  _argName_ 参数的值，ARG 返回的值。  <br/> |
   
## <a name="remarks"></a>备注

作为形状开发人员，您可以通过将某个表达式放置在一个单元格中并从一个或多个其他单元格调用该表达式来创建自定义函数。该表达式可以包括文字字符串、ShapeSheet 函数和单元格引用。该表达式也可以包括由调用单元格传递的特定参数。 
  
调用单元格指定包含自定义函数以及它希望传递给该函数的任何参数的单元格。 将会对表达式单元格进行计算，并将计算结果返回到调用单元格。
  
## <a name="example"></a>示例

以下示例显示了如何将 ARG 函数与 EVALCELL 函数一起使用，以查找一组三个值的中间值。 
  
在表达式单元格中，放置定义自定义函数的以下代码： 
  
```vb
User.MiddleValue = IF(ARG("A")>ARG("B"),IF(ARG("B")>ARG("C"),ARG("B"),IF(ARG("A")>ARG("C"),ARG("C"),ARG("A"))),IF(ARG("A")>ARG("C"),ARG("A"),IF(ARG("B")>ARG("C"),ARG("C"),ARG("B"))))
```

在调用单元格中，放置调用自定义函数的以下代码：
  
```vb
User.Middle1 = EVALCELL(User.MiddleValue,"A",3,"B",9,"C",5) 
User.Middle2 = EVALCELL(User.MiddleValue,"A",12,"B",0,"C",21) 

```


