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
ms.openlocfilehash: c0a12aa18f4c766ea1f5b0fa1d827804d766713c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435710"
---
# <a name="pnt-function"></a>PNT 函数

以单个值的形式返回以_x_轴和_y 轴_坐标表示的点。 
  
## <a name="syntax"></a>语法

PNT (* * *x, y* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _x、y_ <br/> |必需  <br/> |**Number, Number** <br/> |用当前形状的坐标系表示的点的坐标。  <br/> |
   
### <a name="return-value"></a>返回值

Point
  
## <a name="remarks"></a>说明

将坐标转换为磅使您可以更改形状的几何图形, 而无需分别处理*x*坐标和*y*坐标。 
  
## <a name="example"></a>示例

PNT (PinX, PinY) 
  
返回由 PinX 和 PinY 表示的点。 
  

