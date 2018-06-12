---
title: ANGLETOPAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253218
localization_priority: Normal
ms.assetid: 4d87313a-c09a-582c-04f4-d95800e3e9f2
description: 目标形状的父坐标系统中返回已转换的角度。 将源形状中的本地坐标表示角度转换到目标形状中的父坐标。
ms.openlocfilehash: 3a739c55d568dc548f8175b56f22e6ec4c28e4c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779654"
---
# <a name="angletopar-function"></a>ANGLETOPAR 函数

目标形状的父坐标系统中返回已转换的角度。 将源形状中的本地坐标表示角度转换到目标形状中的父坐标。 
  
## <a name="syntax"></a>语法

ANGLETOPAR (* * *srcAngle* * *，* * *srcRef* * *，* * *dstRef* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcAngle_ <br/> |必需  <br/> |**数字** <br/> |源坐标系中的角度。  <br/> |
| _srcRef_ <br/> |必需  <br/> |**字符串** <br/> | 对源对象（如形状、组合、页等）中的单元格的引用。  <br/> |
| _dstRef_ <br/> |必需  <br/> |**字符串** <br/> |对目标对象（如形状、组合、页等）中的单元格的引用。  <br/> |
   
## <a name="remarks"></a>注解

即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。
  
源坐标和目标坐标必须位于同一页上。
  
如果目标是没有父级的页，则将用页的本地坐标表示结果。
  

