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
description: 返回折线。 PolyLineTo geometry 行的一个单元格中使用此函数。
ms.openlocfilehash: afe31b3963cca03d0273b8768f6cc5538d1850ee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780881"
---
# <a name="polyline-function"></a>POLYLINE 函数

返回折线。 PolyLineTo geometry 行的一个单元格中使用此函数。 
  
## <a name="syntax"></a>语法

折线 (* * *xType* * *，* * *yType* * *，* * *x1* * *，* * *y1* * *...) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _xType_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何解释_x_输入的数据。 如果_xType_是 0，则输入的_x_-数据被解释为宽度的百分比。 如果_xType_是 1，则输入的_x_的数据将被解释为本地坐标。  <br/> |
| _yType_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何解释_y_-输入数据。 如果_yType_为 0，输入_y_-数据被解释为高度的百分比。 如果_yType_是 1，则输入_y_-数据将被解释为本地坐标。  <br/> |
| _x1_ <br/> |必需  <br/> |**编号** <br/> | _X_-协调。  <br/> |
| _y1_ <br/> |必需  <br/> |**编号** <br/> |_Y_-协调。  <br/> |
   
## <a name="remarks"></a>说明

对于每一个*x*参数，必须有一个*y*参数;否则，将返回错误。 
  
## <a name="example"></a>示例

POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0) 
  
返回大小为宽 x 高的矩形。 
  

