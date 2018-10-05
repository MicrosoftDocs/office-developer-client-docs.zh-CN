---
title: RECTSECT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251486
localization_priority: Normal
ms.assetid: e83343c5-df5f-bf74-f854-6380176693a2
description: 计算 x 相关联的矩形的扇区和 y，并返回一个整数 0 到 4，指示扇区。
ms.openlocfilehash: fb7ed37ac498765e21c62d7180413cdbcb932502
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395082"
---
# <a name="rectsect-function"></a>RECTSECT 函数

计算矩形*x*和*y*相关联的扇区并返回一个指示扇区的整数 0 到 4。 
  
## <a name="syntax"></a>语法

RECTSECT (* **宽度** *，* **高度** *，* * *x* * *，* * *y* * *，* **选项** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _width_ <br/> |必需  <br/> |**字符串** <br/> |矩形的宽度。  <br/> |
| _height_ <br/> |必需  <br/> |**字符串** <br/> |矩形的高度。  <br/> |
| _x_ <br/> |必需  <br/> |**字符串** <br/> |x 坐标。  <br/> |
| _y_ <br/> |必需  <br/> |**字符串** <br/> |y 坐标。  <br/> |
| _选项_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何处理对角线上的点。将该值设置为 0，表示将左右部分用作对角线上的点。将该值设置为 1，表示将上下部分用作对角线上的点。  <br/> |
   
## <a name="remarks"></a>注解

请考虑矩形的*宽度*和*高度*，从该矩形的中心点点 （*x，y*）。 绘制通过要划分为四个部分和中心点的矩形的对角线。 扇区 0 到 4 表示中心点、 右、 top、 左，并分别下。 
  
![扇区 0 到 4 表示中心点、 右、 top、 左，并分别下](media/ShpSheetRef_CA_03_ZA07645862.gif)
  
## <a name="example"></a>示例

RECTSECT(1 in, 2 in, 1 in, -7 in, 0) 
  
返回 4。 
  

