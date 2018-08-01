---
title: MSOSHADE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 905cd1cc-14d3-5d37-89c4-f8461a03dda2
description: 通过将颜色的发光度降低指定的百分比来修改颜色。
ms.openlocfilehash: f5f6eb0b6009473dcec017e951cca2f90b6c4d55
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780780"
---
# <a name="msoshade-function"></a>MSOSHADE 函数

通过将颜色的发光度降低指定的百分比来修改颜色。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

MSOSHADE (* **颜色** *，* * *-deltaLum* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**RGB** <br/> |标准 RGB（红、绿、蓝）颜色值或对颜色的引用。  <br/> |
| _-deltaLum_ <br/> |必需  <br/> |**Integer** <br/> |更改百分比白色 (-100%) 或黑色 （100%)_颜色_值。  <br/> |
   
## <a name="remarks"></a>说明

越接近_color_值越接近白色或黑色，对底纹由特定 _-deltaLum_值所产生的较小的更改。 
  

