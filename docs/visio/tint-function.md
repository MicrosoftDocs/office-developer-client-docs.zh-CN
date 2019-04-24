---
title: TINT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c4f176d6-4af0-282d-5640-7d98e84dfb55
description: 通过按 int 参数中指定的量 (正数或负数) 增加亮度来修改颜色。
ms.openlocfilehash: 8924bc0662814e14d01b4bd5332f5fadeb0a1082
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280929"
---
# <a name="tint-function"></a>TINT 函数

通过按_int_参数中指定的量 (正数或负数) 增加亮度来修改颜色。 
  
## <a name="syntax"></a>语法

淡色 (* * *color* * *, * * *int* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**Numeric** <br/> |Microsoft Visio 颜色的颜色索引或 RGB 值。  <br/> |
| _int_ <br/> |必需  <br/> |**Integer** <br/> |颜色发光度降低的数量。 可以是正数或负数。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>注解

发光度的上限和下限分别为 0 和 240。 对于可以传递给_int_参数的整数大小没有限制, 但发光度不会超过这些限制。 
  

