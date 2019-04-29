---
title: MSOSHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 905cd1cc-14d3-5d37-89c4-f8461a03dda2
description: 通过将颜色的发光度降低指定的百分比来修改颜色。
ms.openlocfilehash: 207893552c7378589d4a648bf29ed88fcfd15224
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414492"
---
# <a name="msoshade-function"></a>MSOSHADE 函数

通过将颜色的发光度降低指定的百分比来修改颜色。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

MSOSHADE (* * *color* * *, * * *-deltaLum* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**RGB** <br/> |标准 RGB（红、绿、蓝）颜色值或对颜色的引用。  <br/> |
| _-deltaLum_ <br/> |必需  <br/> |**Integer** <br/> |白色的百分比变化 (-100%)或黑色 (100%)从_颜色_值。  <br/> |
   
## <a name="remarks"></a>说明

_颜色_值越接近白色或黑色, 对由特定_deltaLum_值生成的底纹的更改越小。 
  

