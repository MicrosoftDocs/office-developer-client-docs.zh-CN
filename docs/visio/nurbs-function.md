---
title: NURBS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251579
localization_priority: Normal
ms.assetid: f34db20d-6501-2026-a5e8-29c4d4cb2405
description: 返回 NURBS (非均匀有理 B 样) 。 此函数在 NURBSTo 几何图形行的 E 单元格中使用。
ms.openlocfilehash: af92374a829c0df8e71ac81e630abc4fa64988dc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438454"
---
# <a name="nurbs-function"></a>NURBS 函数

返回 NURBS (非均匀有理 B 样) 。 此函数在 NURBSTo 几何图形行的 E 单元格中使用。
  
## <a name="syntax"></a>语法

NURBS (** *knotLast* **， ** *degree* **， ** *xType* **， ** *yType* **， ** *x1* **， ** *y1* **， ** *knot1* **， ** *weight1* **， ...)  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _knotLast_ <br/> |必需  <br/> |**string** <br/> | 最后一个节点。  <br/> |
| _degree_ <br/> |必需  <br/> |**Numeric** <br/> |样条的度数。  <br/> |
| _xType_ <br/> |必需  <br/> |**Numeric** <br/> |指定如何解释 x  _输入_ 数据。 如果  _xType_ 为 0，则所有  _x_ 输入数据都将被解释为 Width 的百分比。 如果  _xType_ 为 1，则所有  _x_ 输入数据都将被解释为本地坐标。  <br/> |
| _yType_ <br/> |必需  <br/> |**Numeric** <br/> |指定如何解释  _y 输入_ 数据。 如果  _yType_ 为 0，则  _所有 y_ 输入数据都将被解释为高度的百分比。 如果  _yType_ 为 1，则  _所有 y_ 输入数据都将被解释为本地坐标。  <br/> |
| _x1_ <br/> |必需  <br/> |**String** <br/> |x 坐标。  <br/> |
| _y1_ <br/> |必需  <br/> |**String** <br/> |y 坐标。  <br/> |
| _knot1_ <br/> |必需  <br/> |**String** <br/> |B 样条上的节点。  <br/> |
| _weight1_ <br/> |必需  <br/> |**String** <br/> |B 样条的粗细。  <br/> |
   
## <a name="remarks"></a>备注

对于每个  *x*  参数，都必须有  *一个 y*  参数;否则，将返回错误。 
  
必须至少指定一个 *x、y、knot* 和 *weight* 参数; 否则，Visio返回错误。 
  

