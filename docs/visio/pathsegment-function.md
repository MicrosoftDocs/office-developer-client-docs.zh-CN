---
title: PATHSEGMENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 08accf3b-93ac-9dd3-85ce-34ad42e79a4f
description: 返回在指定路径指定的百分比标记处 1 开始的线段数。
ms.openlocfilehash: b25f43ffa3c719cfc5ffbd1e417f2da9640e483b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780855"
---
# <a name="pathsegment-function"></a>PATHSEGMENT 函数

返回在指定路径指定的百分比标记处 1 开始的线段数。
  
## <a name="syntax"></a>语法

PATHSEGMENT (* **部分** *，* **差旅** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _section_ <br/> |必需  <br/> |**字符串** <br/> |Geometry 节代表路径，通过对其 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
| _出差_ <br/> |必需  <br/> |**Double** <br/> |从起点到终点经过的路径的百分比。必须为介于 0 和 1 之间的值。  <br/> |
   
### <a name="return-value"></a>返回值

Integer
  

