---
title: NEARESTPOINTONPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 539bf79a-df09-2048-2aba-8c863dd26fc2
description: 返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。
ms.openlocfilehash: ced20cdf1f3531eafaa03c2666b09334029fd3da
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407331"
---
# <a name="nearestpointonpath-function"></a>NEARESTPOINTONPATH 函数

返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

NEARESTPOINTONPATH (* * *section* * *, * * *x* * *, * * *y* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _x_ <br/> |必需  <br/> |**Double** <br/> |指定点的_x_坐标。  <br/> |
| _y_ <br/> |必需  <br/> |**Double** <br/> |指定点的_y_坐标。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>备注

如果_section_不存在, Microsoft Visio 将返回 #REF!。 
  

