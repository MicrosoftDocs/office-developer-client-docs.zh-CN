---
title: USERUI 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251511
localization_priority: Normal
ms.assetid: c01dd938-677c-b2ba-8f56-4638e7e988fd
description: 计算的状态的两个表达式根据值之一。
ms.openlocfilehash: 2cfdf23986a06dcc109106bd50a1a38e5af91313
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781615"
---
# <a name="userui-function"></a>USERUI 函数

计算的_状态_的两个表达式根据值之一。
  
## <a name="syntax"></a>语法

USERUI (* **状态** *，* * *defaultexpression* * *，* * *userexpression* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _state_ <br/> |必需  <br/> |**Boolean** <br/> |确定要计算的表达式。  <br/> |
| _defaultexpression_ <br/> |必需  <br/> |**字符串** <br/> |默认表达式。  <br/> |
| _userexpression_ <br/> |必需  <br/> |**字符串** <br/> |为用户提供一个表达式。  <br/> |
   
## <a name="remarks"></a>备注

如果_状态_为 0，则 USERUI 函数计算_defaultexpression_。 如果_状态_为 1，则其值_userexpression_。
  
## <a name="example"></a>示例

USERUI (1，如果 (宽度\>6 中、 6 英寸，宽度)，宽度\*0.75) 
  
计算表达式 Width\*.075，并返回结果。 
  

