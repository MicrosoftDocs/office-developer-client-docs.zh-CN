---
title: FLOOR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251423
localization_priority: Normal
ms.assetid: 6788bc96-cc86-5f21-781f-67274e7f605a
description: 将数值向 0（零）舍入为下一个整数或 multiple 的下一个实例。
ms.openlocfilehash: 7a16a77a990180f34dd7a5706c24ec3232438467
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439896"
---
# <a name="floor-function"></a>FLOOR 函数

将数字向 0 (零) 舍入到下一个整数或多个 的下一  _个实例_。
  
## <a name="syntax"></a>语法

FLOOR (** *number* **， ** *multiple* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要舍入的数字。  <br/> |
| _multiple_ <br/> |必需  <br/> |**Number** <br/> |要舍入到的倍数。  <br/> |
   
### <a name="return-value"></a>返回值

帐号
  
## <a name="remarks"></a>备注

如果  _未指定 multiple，_ 则数字向 0 舍入为下一个整数。 
  
 _Number_ 和  _multiple_ 必须具有相同的符号，否则#NUM！ 错误。 如果 _数字或__多个_ 不能转换为值，则#VALUE！ 错误。 如果  _number_ 或  _multiple_ 为 0，则结果为 0。 
  
## <a name="example-1"></a>示例 1

FLOOR (3.7) 
  
返回 3。
  
## <a name="example-2"></a>示例 2

FLOOR (-3.7) 
  
返回 -3。
  
## <a name="example-3"></a>示例 3

FLOOR (3.7， 0.5) 
  
返回 3.5。
  

