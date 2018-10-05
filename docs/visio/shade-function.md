---
title: SHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4b4fbcb8-1ae4-c9fb-6337-b72f49aedd91
description: 修改颜色的发光度降低量 （正数或负数） int 参数中指定。
ms.openlocfilehash: b31b4c49a823ace3f6474b94ba3737791928520d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382979"
---
# <a name="shade-function"></a>SHADE 函数

修改颜色的发光度降低量 （正数或负数） _int_参数中指定。 
  
## <a name="syntax"></a>语法

%底纹 (* **颜色** *，* * *int* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**Numeric** <br/> |Microsoft Visio 颜色的颜色索引或 RGB 值。  <br/> |
| _int_ <br/> |必需  <br/> |**Integer** <br/> |颜色发光度降低的数量。可以是正数或负数。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>说明

发光度的上限和下限限制分别为 0 和 240。 您可以为_int_参数，传递的整数的大小没有限制，但发光度不能超过这些限制。 
  
![发光度上下限](media/image199_ZA10173627.gif)
  

