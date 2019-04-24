---
title: AND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251391
localization_priority: Normal
ms.assetid: 434d7ceb-1050-c667-fb3d-b6634440c18e
description: 如果提供的所有逻辑表达式都为 TRUE，则返回 TRUE (1)。如果其中有任何逻辑表达式为 FALSE 或 0，则 AND 函数返回 FALSE (0)。
ms.openlocfilehash: 74e8301718e69a2ab61f6bf9992d0d6855bbc6f1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341557"
---
# <a name="and-function"></a>AND 函数

如果提供的所有逻辑表达式都为 TRUE，则返回 TRUE (1)。如果其中有任何逻辑表达式为 FALSE 或 0，则 AND 函数返回 FALSE (0)。
  
## <a name="syntax"></a>语法

AND (* **逻辑表达式*1 * *, * **逻辑表达式*2 * *,..., * **逻辑 expressionN* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _逻辑表达式_ <br/> |必需  <br/> |**String** <br/> | 常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。任何计算结果等于非零值的表达式都被视为 TRUE。  <br/> |
   
## <a name="example"></a>示例

和 (Height \> 1, PinX \> 1)
  
如果两个表达式都是 TRUE，则返回 TRUE。 如果任意一个表达式为 FALSE，则返回 FALSE。
  

