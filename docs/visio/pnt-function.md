---
title: PNT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251480
localization_priority: Normal
ms.assetid: d14a735c-0278-922f-7823-79adf6cb1e64
description: 以单个值的形式返回使用坐标 x 和 y 表示的点。
ms.openlocfilehash: be00f7d5ae55f70407e35eca43881a6d3f70ec13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780934"
---
# <a name="pnt-function"></a>PNT 函数

返回由坐标_x_和_y_作为单个值表示的点。 
  
## <a name="syntax"></a>语法

PNT (* * *x、 y* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _x y_ <br/> |必需  <br/> |**Number, Number** <br/> |用当前形状的坐标系表示的点的坐标。  <br/> |
   
### <a name="return-value"></a>返回值

Point
  
## <a name="remarks"></a>注解

将坐标转换为磅允许您更改形状的几何图形，而无需处理*x*和*y* -单独坐标。 
  
## <a name="example"></a>示例

PNT(PinX,PinY) 
  
返回由 PinX 和 PinY 表示的点。 
  

