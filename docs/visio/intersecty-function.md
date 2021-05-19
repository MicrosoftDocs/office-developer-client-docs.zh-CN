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
description: 返回本地坐标 (坐标系统坐标) 两条线相交的点中的 y 坐标坐标。
ms.openlocfilehash: 6fcd06e7086d52b9c45f1deb9d4c191f1a7b1fd2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426098"
---
# <a name="intersecty-function"></a>INTERSECTY 函数

返回本地坐标系 (坐标坐标的  *y*  坐标) 两条线相交的点。 
  
## <a name="syntax"></a>语法

INTERSECTX (** *x1* **， ** *y1* **， ** *angle1* **， ** *x2* **， ** *y2* **， ** *angle2* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _x1_ <br/> |必需  <br/> |**Number** <br/> |第  _一_ 行上点的 x 坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**Number** <br/> |第一条直线上的点的  _y_ 坐标。  <br/> |
| _angle1_ <br/> |必需  <br/> |**Number** <br/> | 第一条直线的 Angle 单元格的值。  <br/> |
| _x2_ <br/> |必需  <br/> |**Number** <br/> |第  _二_ 条直线上的点的 x 坐标。  <br/> |
| _y2_ <br/> |必需  <br/> |**Number** <br/> |第二条直线上的点的  _y_ 坐标。  <br/> |
| _angle2_ <br/> |必需  <br/> |**Number** <br/> |第二条直线的 Angle 单元格的值。  <br/> |
   
### <a name="return-value"></a>返回值

帐号
  
## <a name="remarks"></a>备注

每一条直线都可以定义为一个点 (*x,y*) 和一个角。 
  
Microsoft Visio 在粘附到旋转参考线的形状的 PinY 单元格中使用此函数。 
  
如果直线未相交，则该函数将返回被零除错误 (#DIV/0!)，Visio 将忽略此错误，并还原该点的前一个已知值。 
  
## <a name="example"></a>示例

INTERSECTY (VertGuide！PinX，VertGuide！PinY，VertGuide！Angle、HorzGuide！PinX，HorzGuide！PinY，HorzGuide！角度)  
  
返回 VertGuide 和 HorzGuide 的交点（以页面单位表示）的  *y*  坐标。 
  

