---
title: TONE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2d6a7dd-9f15-27bd-9623-2a047683ff98
description: 通过将其饱和度降低为 int 参数中指定的数量来修改颜色。
ms.openlocfilehash: c3352d4c15671244d0fc4701f2c26b4e0c2ea54d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434373"
---
# <a name="tone-function"></a>TONE 函数

通过将其饱和度降低为_int_参数中指定的数量来修改颜色。 
  
## <a name="syntax"></a>语法

音调 (* * *color* * *, * * *int* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**数值** <br/> |Microsoft Visio 颜色的颜色索引或 RGB 值。  <br/> |
| _int_ <br/> |必需  <br/> |**Integer** <br/> |颜色饱和度降低的数量。 可以是正数或负数。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>说明

饱和度的上下限分别为 0 和 240。 对于可以传递给_int_参数的整数大小没有限制, 但饱和度不会超过这些限制。 
  

