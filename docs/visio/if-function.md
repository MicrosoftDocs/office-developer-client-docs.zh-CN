---
title: IF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251442
localization_priority: Normal
ms.assetid: 66771ad3-0fb3-68ff-81da-d1162d37c05a
description: 如果 logicalexpression 为 TURE，则返回 valueiftrue。 否则，将返回 valueiffalse。
ms.openlocfilehash: 8780bd3dd5ded1a950a5bf3f79333687f3b6843c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405469"
---
# <a name="if-function"></a>IF 函数

如果_logicalexpression_为 TRUE, 则返回_valueiftrue_ 。 否则, 它将返回_valueiffalse_。
  
## <a name="syntax"></a>语法

如果 (* * *logicalexpression* * *, * * *valueiftrue* * *, * * *valueiffalse* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _logicalexpression_ <br/> |必需  <br/> |**String** <br/> |要计算的表达式。  <br/> |
| _valueiftrue_ <br/> |必需  <br/> |**相同** <br/> |_logicalexpression_为 true 时要返回的值。  <br/> |
| _valueiffalse_ <br/> |必需  <br/> |**相同** <br/> | _logicalexpression_为 false 时要返回的值。  <br/> |
   
### <a name="return-value"></a>返回值

各不相同
  
## <a name="example"></a>示例

IF (Height \> 1.25 in, 5, 7)
  
如果形状的高度大于 1.25 英寸，则返回 5。 如果形状的高度小于或等于 1.25 英寸，则返回 7。
  

