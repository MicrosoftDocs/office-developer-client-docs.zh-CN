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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406421"
---
# <a name="msotint-function"></a>MSOTINT 函数

通过将颜色的发光度增加指定的百分比来修改颜色。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

MSOTINT (** *color* **， ** *deltaLum* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _color_ <br/> |必需  <br/> |**RGB** <br/> |标准 RGB（红、绿、蓝）颜色值或对颜色的引用。  <br/> |
| _deltaLum_ <br/> |必需  <br/> |**Integer** <br/> |从颜色值 (到 100%) 或黑色 (100%) 的百  _分比_ 变化。  <br/> |
   
## <a name="remarks"></a>备注

颜色值  _越_ 接近白色或黑色，由特定  _deltaLum_ 值产生的淡色变化越小。 
  

