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
description: 在 SETATREF 函数的 set_expression 参数中使用, 以指示在将 set_expression 分配给 SETATREF 中的 reference 参数之前应计算。
ms.openlocfilehash: a11a7485e04d4deb31e9497476bb198d675bc68f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432980"
---
# <a name="setatrefeval-function"></a>SETATREFEVAL 函数

在 SETATREF 函数的_set_expression_参数中使用, 以指示在将 set_expression 分配给 SETATREF 中的_reference_参数之前应计算__ 。 
  
## <a name="syntax"></a>语法

SETATREFEVAL (* * *expr* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expr_ <br/> |必需  <br/> |**相同** <br/> | 当 SETATREF 函数将_set_expression_重定向到另一个单元格时计算的表达式。  <br/> |
   
## <a name="remarks"></a>说明

为引用的单元格分配 SETATREF 函数的*set_expression*参数时, 默认情况下, Microsoft Visio 会将*set_expression*作为表达式写入单元格。 但是, 如果 SETATREFEVAL 函数封装了*set_expression*参数的任何部分, Visio 将对表达式进行求值, 并在解析 SETATREF 表达式之前将 SETATREFEVAL 函数替换为其结果。 
  
## <a name="example"></a>示例

有关示例，请参阅 [SETATREF](setatref-function.md) 函数。 
  

