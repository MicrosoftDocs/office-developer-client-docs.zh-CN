---
title: PATHSEGMENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 08accf3b-93ac-9dd3-85ce-34ad42e79a4f
description: 返回指定路径上指定百分比标记的从 1 到的线段编号。
ms.openlocfilehash: c4dfc4d33de1a9c1a03ef14d76103b4de0f28bc7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432483"
---
# <a name="pathsegment-function"></a>PATHSEGMENT 函数

返回指定路径上指定百分比标记的从 1 到的线段编号。
  
## <a name="syntax"></a>语法

PATHSEGMENT (** *section* **， ** *travel* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _travel_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点经过的路径的百分比。必须为介于 0 和 1 之间的值。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  

