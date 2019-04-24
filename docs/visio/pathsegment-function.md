---
title: PATHSEGMENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 08accf3b-93ac-9dd3-85ce-34ad42e79a4f
description: 返回一个从1开始的段落编号, 位于指定的百分比标记处沿指定的路径。
ms.openlocfilehash: c4dfc4d33de1a9c1a03ef14d76103b4de0f28bc7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344448"
---
# <a name="pathsegment-function"></a>PATHSEGMENT 函数

返回一个从1开始的段落编号, 位于指定的百分比标记处沿指定的路径。
  
## <a name="syntax"></a>语法

PATHSEGMENT (* * *section* * *、* **差旅** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**String** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _传输_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点经过的路径的百分比。 必须为介于 0 和 1 之间的值。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  

