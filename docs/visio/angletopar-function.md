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
description: 用目标形状的父坐标系返回一个转换过的角度。 它将一个角度从源形状中的本地坐标转换为目标形状中的父坐标。
ms.openlocfilehash: e411cbae21d832039e2fbda93393a8fe0bd1f9f8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404321"
---
# <a name="angletopar-function"></a>ANGLETOPAR 函数

用目标形状的父坐标系返回一个转换过的角度。 它将一个角度从源形状中的本地坐标转换为目标形状中的父坐标。 
  
## <a name="syntax"></a>语法

ANGLETOPAR (* * *srcAngle* * *, * * *srcRef* * *, * * *dstRef* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcAngle_ <br/> |必需  <br/> |**数值** <br/> |源坐标系中的角度。  <br/> |
| _srcRef_ <br/> |必需  <br/> |**String** <br/> | 对源对象（如形状、组合、页等）中的单元格的引用。  <br/> |
| _dstRef_ <br/> |必需  <br/> |**String** <br/> |对目标对象（如形状、组合、页等）中的单元格的引用。  <br/> |
   
## <a name="remarks"></a>说明

即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。
  
源坐标和目标坐标必须位于同一页上。
  
如果目标是没有父级的页，则将用页的本地坐标表示结果。
  

