---
title: MSOTINT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bae0af9-229d-e114-4feb-bf6d7a7d8b08
description: 通过将颜色的发光度增加指定的百分比来修改颜色。
ms.openlocfilehash: d63b90d0cd6fcb35e23a8efa4ca9e13e2838bc21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335194"
---
# <a name="msotint-function"></a>MSOTINT 函数

通过将颜色的发光度增加指定的百分比来修改颜色。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

MSOTINT (* * *color* * *, * * *deltaLum* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**RGB** <br/> |标准 RGB（红、绿、蓝）颜色值或对颜色的引用。  <br/> |
| _deltaLum_ <br/> |必需  <br/> |**Integer** <br/> |白色的百分比变化 (-100%)或黑色 (100%)从_颜色_值。  <br/> |
   
## <a name="remarks"></a>注解

_颜色_值越接近白色或黑色, 对由特定_deltaLum_值生成的色调所做的更改越小。 
  

