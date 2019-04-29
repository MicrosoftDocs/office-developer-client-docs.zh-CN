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
description: 返回形状的父级坐标系中某个点的 x, y 坐标。
ms.openlocfilehash: 4e7517c4210db31f1c3f5dc8bf98185b6f4104aa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414506"
---
# <a name="par-function"></a>PAR 函数

返回形状的父级坐标系中某个点的_x, y_坐标。 
  
## <a name="syntax"></a>语法

PAR (* **点** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _鼠标_ <br/> |必需  <br/> |**Number, Number** <br/> |用当前形状的坐标系表示的点的坐标。  <br/> |
   
## <a name="remarks"></a>说明

在 Microsoft Visio 中, 点是一个体现一对*x*和*y*坐标的单个值。 如果形状在一个组合中，则它的父级就是该组合。 如果形状不在一个组合中，则它的父级是页。 
  
## <a name="example"></a>示例

PAR (PNT (PinX, PinY)) 
  
在此表达式中，PNT 将当前形状中的一对坐标转换为一个点。然后，PAR 再将这个点转换为相对于包含当前形状的页或组合的左下角的一对坐标。 
  

