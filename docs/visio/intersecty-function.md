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
description: 返回两条线相交的点的 y 轴坐标值 (在本地坐标系中)。
ms.openlocfilehash: 6fcd06e7086d52b9c45f1deb9d4c191f1a7b1fd2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335257"
---
# <a name="intersecty-function"></a>INTERSECTY 函数

返回两条线相交的点的*y*轴坐标值 (在本地坐标系中)。 
  
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

帐号
  
## <a name="remarks"></a>注解

每一条直线都可以定义为一个点 (*x,y*) 和一个角。 
  
Microsoft Visio 在粘附到旋转参考线的形状的 PinY 单元格中使用此函数。 
  
如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。 
  
## <a name="example"></a>示例

INTERSECTY (VertGuide!PinX、VertGuide!PinY、VertGuide!角、用 horzguide!PinX、用 horzguide!PinY、用 horzguide!Angle 
  
返回 VertGuide 和用 horzguide 的交集点的*y*坐标 (以页面单位表示)。 
  

