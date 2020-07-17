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
description: 计算与 x 和 y 相关联的矩形的扇区，并返回整数0到4，指示扇区。
ms.openlocfilehash: 442ec0d614589c709a097ba314abad044d470df6
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160270"
---
# <a name="rectsect-function"></a>RECTSECT 函数

计算与*x*和*y*相关联的矩形的扇区，并返回整数0到4，指示扇区。 
  
## <a name="syntax"></a>语法

RECTSECT （***width***， ***height***， ***x***， ***y***， ***option*** ） 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _width_ <br/> |必需  <br/> |**字符串** <br/> |矩形的宽度。  <br/> |
| _height_ <br/> |必需  <br/> |**字符串** <br/> |矩形的高度。  <br/> |
| _x_ <br/> |必需  <br/> |**字符串** <br/> |x 坐标。  <br/> |
| _y_ <br/> |必需  <br/> |**字符串** <br/> |y 坐标。  <br/> |
| _可选_ <br/> |必需  <br/> |**Boolean** <br/> |指定如何处理对角线上的点。将该值设置为 0，表示将左右部分用作对角线上的点。将该值设置为 1，表示将上下部分用作对角线上的点。  <br/> |
   
## <a name="remarks"></a>注解

假设有一个*宽度*和*高度*的矩形，以及该矩形的中心点的点（*x，y*）。 绘出矩形的对角线，从而将矩形划分为四个部分和一个中心点。 0 到 4 部分分别代表中心点、右、上、左和下。 
  
![0到4扇区分别代表中心点、右边、顶部、左侧和底部](media/ShpSheetRef_CA_03_ZA07645862.gif)
  
## <a name="example"></a>示例

RECTSECT(1 in, 2 in, 1 in, -7 in, 0) 
  
返回 4。 
  

