---
title: INTERSECTY 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251445
localization_priority: Normal
ms.assetid: a298eead-044b-6f40-54c7-e0e6088baa19
description: 返回 y-两个线相交的点的坐标 （以本地坐标系表示）。
ms.openlocfilehash: c3c0e9afef317ed4c647f1d236c4c3a29c6cdaa6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780460"
---
# <a name="intersecty-function"></a>INTERSECTY 函数

返回*y* -两个线相交的点的坐标 （以本地坐标系表示）。 
  
## <a name="syntax"></a>语法

INTERSECTX (* * *x1* * *，* * *y1* * *，* **角度 1* * *，* * *x2* * *，* * *y2* * *，* **角度 2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _x1_ <br/> |必需  <br/> |**编号** <br/> |_X_-第一个线上某个点的坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**编号** <br/> |_Y_-第一个线上某个点的坐标。  <br/> |
| _角度 1_ <br/> |必需  <br/> |**编号** <br/> | 第一条直线的 Angle 单元格的值。  <br/> |
| _x2_ <br/> |必需  <br/> |**编号** <br/> |_X_-第二个线上某个点的坐标。  <br/> |
| _y2_ <br/> |必需  <br/> |**编号** <br/> |_Y_-第二个线上某个点的坐标。  <br/> |
| _角度 2_ <br/> |必需  <br/> |**编号** <br/> |第二条直线的 Angle 单元格的值。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>说明

每一条直线都可以定义为一个点 (*x,y*) 和一个角。 
  
Microsoft Visio 在粘附到旋转参考线的形状的 PinY 单元格中使用此函数。 
  
如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。 
  
## <a name="example"></a>示例

INTERSECTY (VertGuide ！PinX，VertGuide ！PinY，VertGuide ！角度，HorzGuide ！PinX，HorzGuide ！PinY，HorzGuide ！角度） 
  
返回*y* -以页面单位表示的交点 VertGuide 和 HorzGuide 的坐标。 
  

