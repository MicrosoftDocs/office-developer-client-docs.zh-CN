---
title: INTERSECTX 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251444
localization_priority: Normal
ms.assetid: d8dc1915-f055-e858-1323-9e8c1cb7f2f1
description: 返回两条直线相交点的 x 轴坐标值 (在局部坐标系中)。
ms.openlocfilehash: 857f81d667e33ad9ce79405ef5d59874903098e6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418272"
---
# <a name="intersectx-function"></a>INTERSECTX 函数

返回两条直线相交点的*x*轴坐标值 (在局部坐标系中)。 
  
## <a name="syntax"></a>语法

INTERSECTX (* * *x1* * *、* * *y1* * *、* * *angle1* * *、* * *x2* * *、* * *y2* * *、* * *angle2* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _x1_ <br/> |必需  <br/> |**Number** <br/> |第一条直线上的点的_x_坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**Number** <br/> |第一条直线上的点的_y_坐标。  <br/> |
| _angle1_ <br/> |必需  <br/> |**Number** <br/> | 第一条直线的 Angle 单元格的值。  <br/> |
| _x2_ <br/> |必需  <br/> |**Number** <br/> |第二条直线上的点的_x_坐标。  <br/> |
| _y2_ <br/> |必需  <br/> |**Number** <br/> |第二条直线上的点的_y_轴坐标值。  <br/> |
| _angle2_ <br/> |必需  <br/> |**Number** <br/> |第二条直线的 Angle 单元格的值。  <br/> |
   
### <a name="return-value"></a>返回值

数字
  
## <a name="remarks"></a>说明

每一条直线都可以定义为一个点 (*x,y*) 和一个角。 
  
Microsoft Visio 在粘附到旋转参考线的形状的 PinX 单元格中使用此函数。 
  
如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。 
  
## <a name="example"></a>示例

INTERSECTX (VertGuide!PinX、VertGuide!PinY、VertGuide!角、用 horzguide!PinX、用 horzguide!PinY、用 horzguide!Angle 
  
返回 VertGuide 和用 horzguide 的交叉点的*x*坐标 (以页面单位表示)。 
  

