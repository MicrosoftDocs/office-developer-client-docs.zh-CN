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
description: 返回折线。 此函数用于 PolyLineTo 几何图形行的 A 单元格。
ms.openlocfilehash: d801c6f2c1a81cc5cc99b3517c4d86784421d7e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426294"
---
# <a name="polyline-function"></a>POLYLINE 函数

返回折线。 此函数用于 PolyLineTo 几何图形行的 A 单元格。 
  
## <a name="syntax"></a>语法

POLYLINE (** *xType* **， ** *yType* **， ** *x1* **， ** *y1* **...)  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _xType_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何解释 x  _输入_ 数据。 如果  _xType_ 为 0，则  _输入 x_-data 将被解释为 Width 的百分比。 如果  _xType_ 为 1，则  _输入 x_-data 将被解释为本地坐标。  <br/> |
| _yType_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何解释  _y_-input 数据。 如果  _yType_ 为 0，则  _输入的 y_-data 将被解释为 Height 的百分比。 如果  _yType_ 为 1，则  _输入的 y_-data 将被解释为本地坐标。  <br/> |
| _x1_ <br/> |必需  <br/> |**Number** <br/> | x 坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**Number** <br/> |_y_ 坐标。  <br/> |
   
## <a name="remarks"></a>备注

对于每个  *x*  参数，都必须有  *一个 y*  参数;否则，将返回错误。 
  
## <a name="example"></a>示例

POLYLINE (0, 0, 0, 0, 0, 1, 1, 1, 1, 0, 0, 0) 
  
返回大小为宽 x 高的矩形。 
  

