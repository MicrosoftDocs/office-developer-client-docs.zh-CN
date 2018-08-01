---
title: LOCTOPAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251585
localization_priority: Normal
ms.assetid: ce1028d6-0293-e8dd-b79d-3f02c50f6250
description: 在目标坐标系统中的父坐标返回已转换的点。
ms.openlocfilehash: 7d882ec34de93db2828fc751f99d87fc3e961d64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780682"
---
# <a name="loctopar-function"></a>LOCTOPAR 函数

在目标坐标系统中的父坐标返回已转换的点。
  
## <a name="syntax"></a>语法

LOCTOPAR (* * *srcPoint* * *，* * *srcRef* * *，* * *dstRef* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _srcPoint_ <br/> |必需  <br/> |**字符串** <br/> | 用源坐标系中的本地坐标表示的点。  <br/> |
| _srcRef_ <br/> |必需  <br/> |**字符串** <br/> | 对源对象中的单元格的引用。  <br/> |
| _dstRef_ <br/> |必需  <br/> |**字符串** <br/> | 对目标对象中的单元格的引用。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

将用源形状中的本地坐标表示的点转换为用目标形状中的父坐标表示的点。您可以使用另一个坐标系中的另一个点，通过 LOCTOPAR 函数在单元格中设置父坐标，如形状中的 PinX、PinY、BeginX 和 BeginY。 
  
即使源形状和目标形状都位于组合中，此函数也能够正常工作。它还能够在中间转换中进行旋转和翻转调整。 
  
源坐标和目标坐标必须位于同一页上。 
  
如果目标是没有父项的页，则将用该页的本地坐标表示结果。 
  
## <a name="example"></a>示例

LOCTOPAR(PNT(LocPinX, LocPinY), Width, Sheet.4!Width) 
  
将与公式相关联的形状的本地旋转中心点转换为 Sheet.4 的父坐标。 
  

