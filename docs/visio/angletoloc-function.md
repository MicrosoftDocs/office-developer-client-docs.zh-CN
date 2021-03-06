---
title: ANGLETOLOC 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253217
localization_priority: Normal
ms.assetid: ee5e3898-bb49-57c6-0ebe-12e1fe388e55
description: 使用目标形状的本地坐标系返回一个转换过的角度。它将一个角度从源形状中的本地坐标转换到目标形状中的本地坐标。
ms.openlocfilehash: e971613d4fc33cd991e7e9aeba49ac47871ebe8f
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160263"
---
# <a name="angletoloc-function"></a>ANGLETOLOC 函数

使用目标形状的本地坐标系返回一个转换过的角度。它将一个角度从源形状中的本地坐标转换到目标形状中的本地坐标。
    
 
  
## <a name="syntax"></a>语法

ANGLETOLOC (***srcAngle***、 ***srcRef***、 ***dstRef*** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcAngle_ <br/> |必需  <br/> |**Numeric** <br/> |源坐标系中的角度。  <br/> |
| _srcRef_ <br/> |必需  <br/> |**String** <br/> | 对源对象（如形状、组合、页等）中的单元格的引用。  <br/> |
| _dstRef_ <br/> |必需  <br/> |**String** <br/> |对目标对象（如形状、组合、页等）中的单元格的引用。  <br/> |
   
## <a name="remarks"></a>备注

可以使用 ANGLETOLOC 函数来按照另一个坐标空间中的角度设置形状中的本地角度单元格。
  
即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。
  
源坐标和目标坐标必须位于同一页上。
  

