---
title: POLYLINE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251576
localization_priority: Normal
ms.assetid: 10baeec9-6c9b-b4ba-3138-7d1156a9e056
description: 返回一个折线。 此函数用于 PolyLineTo 几何图形行的的一个单元格。
ms.openlocfilehash: d801c6f2c1a81cc5cc99b3517c4d86784421d7e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426294"
---
# <a name="polyline-function"></a>POLYLINE 函数

返回一个折线。 此函数用于 PolyLineTo 几何图形行的的一个单元格。 
  
## <a name="syntax"></a>语法

折线 (* * *xType* * *, * * *yType* * *, * * ** , * *, * * *y1* * * ...) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _xType_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何解释_x_输入数据。 如果_xType_为 0, 则输入的_x_数据将被解释为宽度的百分比。 如果_xType_为 1, 则输入的_x_数据将被解释为本地坐标。  <br/> |
| _yType_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何解释_y_输入数据。 如果_yType_为 0, 则输入的_y_数据将被解释为高度的百分比。 如果_yType_为 1, 则输入的_y_数据将被解释为本地坐标。  <br/> |
| _x1_ <br/> |必需  <br/> |**Number** <br/> | _x_轴坐标值。  <br/> |
| _y1_ <br/> |必需  <br/> |**Number** <br/> |_y_轴坐标值。  <br/> |
   
## <a name="remarks"></a>说明

对于每个*x*参数, 必须有一个*y*参数;否则, 将返回错误。 
  
## <a name="example"></a>示例

POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0) 
  
返回大小为宽 x 高的矩形。 
  

