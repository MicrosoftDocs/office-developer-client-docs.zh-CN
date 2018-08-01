---
title: PAR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251477
localization_priority: Normal
ms.assetid: 9caf424d-cb70-8f1a-b984-64cf776bdfb4
description: 返回形状的父级的坐标系统中的 x，某一点的 y 坐标。
ms.openlocfilehash: a3f7afd3f9bc988a20526451a6d7d7081d27a2d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780844"
---
# <a name="par-function"></a>PAR 函数

返回形状的父级的坐标系统中的点的_x，y_坐标。 
  
## <a name="syntax"></a>语法

PAR (* **指向** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _磅_ <br/> |必需  <br/> |**Number, Number** <br/> |用当前形状的坐标系表示的点的坐标。  <br/> |
   
## <a name="remarks"></a>说明

Microsoft Visio 中点是一个 single 值它来实现一对*x*和*y* -坐标。 如果形状是组中，其父对象是组。 如果形状不是组中，其父对象是页面。 
  
## <a name="example"></a>示例

PAR(PNT(PinX,PinY)) 
  
在此表达式中，PNT 将当前形状中的一对坐标转换为一个点。然后，PAR 再将这个点转换为相对于包含当前形状的页或组合的左下角的一对坐标。 
  

