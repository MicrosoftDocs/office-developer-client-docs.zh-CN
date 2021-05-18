---
title: SHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4b4fbcb8-1ae4-c9fb-6337-b72f49aedd91
description: 通过按 int 参数中指定的正 (或负值) 颜色来修改颜色。
ms.openlocfilehash: b31b4c49a823ace3f6474b94ba3737791928520d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326593"
---
# <a name="shade-function"></a>SHADE 函数

通过按  _int_ 参数中指定的正数 (或负值) 颜色来修改颜色。 
  
## <a name="syntax"></a>语法

SHADE (** *color* **， ** *int* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**Numeric** <br/> |Microsoft Visio 颜色的颜色索引或 RGB 值。  <br/> |
| _int_ <br/> |必需  <br/> |**Integer** <br/> |颜色发光度降低的数量。可以是正数或负数。  <br/> |
   
### <a name="return-value"></a>返回值

 **RGB**
  
## <a name="remarks"></a>备注

发光度的上限和下限分别为 0 和 240。 对于您可以为  _int_ 参数传递的整数大小没有限制，但亮度永远不会超过这些限制。 
  
![亮度的上限和下限](media/image199_ZA10173627.gif)
  

