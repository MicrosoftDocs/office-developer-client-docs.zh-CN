---
title: SEGMENTCOUNT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 792ec0e4-4a48-136b-904c-fe269e355070
description: 返回组成路径的线段数。
ms.openlocfilehash: 947e37c13de638e4f281bc17376a253a8ca07e04
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326038"
---
# <a name="segmentcount-function"></a>SEGMENTCOUNT 函数

返回组成路径的线段数。
  
## <a name="syntax"></a>语法

SEGMENTCOUNT (* * *pathRef* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _pathRef_ <br/> |必需  <br/> |**Integer** <br/> |代表路径的 Geometry 节，通过对 Path 单元格的引用指定（例如 Geometry1.Path）。  <br/> |
   
### <a name="return-value"></a>返回值

整数
  
## <a name="remarks"></a>注解

返回的线段总数中不包含跨线。
  

