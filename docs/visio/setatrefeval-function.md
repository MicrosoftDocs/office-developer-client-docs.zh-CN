---
title: SETATREFEVAL 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1042150
localization_priority: Normal
ms.assetid: b3f3a0a0-7b14-0b71-d247-ada81b93b66b
description: SETATREF 函数的 set_expression 参数中用于指示该 set_expression 应计算之前将分配给中 SETATREF 引用参数。
ms.openlocfilehash: 0826ef9ca91e180576c0b2611452758b238736a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781235"
---
# <a name="setatrefeval-function"></a>SETATREFEVAL 函数

SETATREF 函数的_set_expression_参数中用于指示在 SETATREF_引用_参数为分配之前应计算_set_expression_的。 
  
## <a name="syntax"></a>语法

SETATREFEVAL (* * *expr* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expr_ <br/> |必需  <br/> |**因情况而异** <br/> | SETATREF 函数将_set_expression_重定向到另一个单元格时计算的表达式。  <br/> |
   
## <a name="remarks"></a>说明

将 SETATREF 函数的*set_expression*参数分配给引用的单元格，Microsoft Visio 将*set_expression*写入单元格表达式作为默认情况下。 但是，如果*set_expression*参数的任何部分由 SETATREFEVAL 函数包装，Visio 将计算表达式并 SETATREFEVAL 函数替换之前解析 SETATREF 表达式及其结果。 
  
## <a name="example"></a>示例

有关示例，请参阅 [SETATREF](setatref-function.md) 函数。 
  

