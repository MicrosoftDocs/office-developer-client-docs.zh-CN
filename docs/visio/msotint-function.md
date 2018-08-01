---
title: MSOTINT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bae0af9-229d-e114-4feb-bf6d7a7d8b08
description: 通过将颜色的发光度增加指定的百分比来修改颜色。
ms.openlocfilehash: 50e81b5202174c61905d3914c50feddcb05a91cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780809"
---
# <a name="msotint-function"></a>MSOTINT 函数

通过将颜色的发光度增加指定的百分比来修改颜色。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

MSOTINT (* **颜色** *，* * *deltaLum* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**RGB** <br/> |标准 RGB（红、绿、蓝）颜色值或对颜色的引用。  <br/> |
| _deltaLum_ <br/> |必需  <br/> |**Integer** <br/> |更改百分比白色 (-100%) 或黑色 （100%)_颜色_值。  <br/> |
   
## <a name="remarks"></a>说明

越接近_color_值越接近白色或黑色，淡色由特定_deltaLum_值所产生的较小更改。 
  

