---
title: OR 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251476
localization_priority: Normal
ms.assetid: 6c2154fa-4190-0699-61f7-f2bdf87173ec
description: 如果任何作为参数传递的逻辑表达式为 TRUE，则返回 TRUE (1)。
ms.openlocfilehash: 14646f553e76c8c395fdbde8762daf75114f9480
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780817"
---
# <a name="or-function"></a>OR 函数

如果任何作为参数传递的逻辑表达式为 TRUE，则返回 TRUE (1)。
  
## <a name="syntax"></a>语法

或者 (* * *logicalexpression1* * *，* * *logicalexpression2* * *，...，* * *logicalexpressionN* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _logicalexpression1_ <br/> |必需  <br/> |**字符串** <br/> |要计算其真实性的第一个表达式。  <br/> |
| _logicalexpression2_ <br/> |必需  <br/> |**字符串** <br/> |要计算其真实性的第二个表达式。  <br/> |
| _logicalexpressionN_ <br/> |必需  <br/> |**字符串** <br/> |要计算其真实性的第 N 个表达式。  <br/> |
   
### <a name="return-value"></a>返回值

Boolean
  
## <a name="remarks"></a>注解

任何计算为非零值的表达式都被视为 TRUE。如果所有逻辑表达式都为 FALSE 或等于 0，则此函数将返回 FALSE。 
  
## <a name="example"></a>示例

或者 (高度\>1，PinX \> 1) 
  
如果两个表达式当中的任意一个为 TRUE，则返回 TRUE (1)。只有当两个表达式都为 FALSE 时，才返回 FALSE (0)。 
  

