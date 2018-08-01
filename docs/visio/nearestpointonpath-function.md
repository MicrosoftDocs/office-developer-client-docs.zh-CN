---
title: NEARESTPOINTONPATH 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 539bf79a-df09-2048-2aba-8c863dd26fc2
description: 返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。
ms.openlocfilehash: d9e9b890033526fec99f04cee30ae93578487652
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780781"
---
# <a name="nearestpointonpath-function"></a>NEARESTPOINTONPATH 函数

返回距指定坐标最近的点沿路径的距离百分比，返回的值介于 0 到 1 之间。
  
## <a name="version-information"></a>版本信息

添加的版本： Visio 2010
 
  
## <a name="syntax"></a>语法

NEARESTPOINTONPATH (* **部分** *，* * *x* * *，* * *y* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**字符串** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _x_ <br/> |必需  <br/> |**Double** <br/> |_X_-指定点的坐标。  <br/> |
| _y_ <br/> |必需  <br/> |**Double** <br/> |_Y_-指定点的坐标。  <br/> |
   
### <a name="return-value"></a>返回值

 **Double**
  
## <a name="remarks"></a>注解

如果_section_不存在，Microsoft Visio 将返回 #REF ！。 
  

