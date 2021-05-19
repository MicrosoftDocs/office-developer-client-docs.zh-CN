---
title: TIME 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251506
localization_priority: Normal
ms.assetid: 2e662230-0760-5f43-52dc-927f499715f6
description: 返回由小时、分钟和秒表示的时间。
ms.openlocfilehash: f5be55d7e63a70d15da49c68b924cc5b03c5ca88
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414471"
---
# <a name="time-function-visioshapesheet"></a>TIME 函数 (VisioShapeSheet)

返回由小时、_分钟和秒_ 表示 _的时间_。
  
## <a name="syntax"></a>语法

TIME (** *hour* **， ** *minute* **， ** second ** *)* 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _hour_ <br/> |必需  <br/> |**Numeric** <br/> |小时成分。  <br/> |
| _minute_ <br/> |必需  <br/> |**Numeric** <br/> |分钟成分。  <br/> |
| _second_ <br/> |必需  <br/> |**Numeric** <br/> |秒成分。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="example-1"></a>示例 1

TIME (15，30，30) 
  
返回表示下午 3:30:30 的值。
  
## <a name="example-2"></a>示例 2

FORMAT (TIME (15，30，30) ，"HH：mm") 
  
返回表示 15:30 的值。
  
## <a name="example-3"></a>示例 3

TIME(15,30,30) + 8 eh.
  
返回表示午夜 11:30:30 的值。
  

