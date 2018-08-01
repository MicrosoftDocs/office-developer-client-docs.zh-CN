---
title: SEGMENTCOUNT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 792ec0e4-4a48-136b-904c-fe269e355070
description: 返回组成路径的线段数。
ms.openlocfilehash: 93a77d9085e6900f502a75401847ad685d25effd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781245"
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

Integer
  
## <a name="remarks"></a>注解

返回的线段总数中不包含跨线。
  

