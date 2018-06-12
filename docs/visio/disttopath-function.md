---
title: DISTTOPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2ba7d372-0c2a-9fa7-0af6-97da0aafdb12
description: 返回由指定坐标表示的点到路径上某一点的最短距离。
ms.openlocfilehash: 227fe860de2e3683b5d7d3e5f9313d1e2e31b2d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780124"
---
# <a name="disttopath-function"></a>DISTTOPATH 函数

返回由指定坐标表示的点到路径上某一点的最短距离。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010 
  
## <a name="syntax"></a>语法

DISTTOPATH (* **部分** *，* * *x* * *，* * *y* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**字符串** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _x_ <br/> |必需  <br/> |**Double** <br/> |_X_-点的坐标。  <br/> |
| _y_ <br/> |必需  <br/> |**Double** <br/> |_Y_-点的坐标。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>注解

Microsoft Visio 将返回 #REF ！ 如果_section_不存在。 
  
如果该点位于移动方向的左侧，则返回的值为正；如果该点位于移动方向的右侧，则返回的值为负。
  

