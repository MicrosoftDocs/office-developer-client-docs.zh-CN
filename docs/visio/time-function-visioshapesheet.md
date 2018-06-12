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
description: 返回时间表示的小时、 分钟和秒。
ms.openlocfilehash: 4390e0cdccf0ae7798d5ada4329a28f72566ecac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781536"
---
# <a name="time-function-visioshapesheet"></a>TIME 函数 (VisioShapeSheet)

返回由_小时_、_分钟_和_秒_的时间。
  
## <a name="syntax"></a>语法

时间 (* **小时** *，* **分钟** *，* **第二个** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _小时_ <br/> |必需  <br/> |**数字** <br/> |小时成分。  <br/> |
| _分钟_ <br/> |必需  <br/> |**数字** <br/> |分钟成分。  <br/> |
| _第二个_ <br/> |必需  <br/> |**数字** <br/> |秒成分。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="example-1"></a>示例 1

TIME(15,30,30)
  
返回表示下午 3:30:30 的值。
  
## <a name="example-2"></a>示例 2

FORMAT(TIME(15,30,30),"HH:mm")
  
返回表示 15:30 的值。
  
## <a name="example-3"></a>示例 3

TIME(15,30,30) + 8 eh.
  
返回表示午夜 11:30:30 的值。
  

