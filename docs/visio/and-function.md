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
ms.openlocfilehash: 27b2ef97ef1d0afde37596b18674c6de26355a1b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779655"
---
# <a name="and-function"></a>AND 函数

如果提供的所有逻辑表达式都为 TRUE，则返回 TRUE (1)。如果其中有任何逻辑表达式为 FALSE 或 0，则 AND 函数返回 FALSE (0)。
  
## <a name="syntax"></a>语法

和 (* **逻辑 expression1* * *，* **逻辑 expression2* * *，...，* **逻辑表达式** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _逻辑表达式_ <br/> |必需  <br/> |**字符串** <br/> | 常量、运算符、函数和对 ShapeSheet 单元格的引用的组合，其结果为一个值。任何计算结果等于非零值的表达式都被视为 TRUE。  <br/> |
   
## <a name="example"></a>示例

和 (高度\>1，PinX \> 1)
  
如果两个表达式都是 TRUE，则返回 TRUE。如果任意一个表达式为 FALSE，则返回 FALSE。
  

