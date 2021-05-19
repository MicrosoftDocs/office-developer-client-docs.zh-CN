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
description: 在 SETATREF set_expression 的 set_expression 参数中用于指示在将set_expression SETATREF 中的引用参数之前应先计算该参数。
ms.openlocfilehash: a11a7485e04d4deb31e9497476bb198d675bc68f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432980"
---
# <a name="setatrefeval-function"></a>SETATREFEVAL 函数

在 SETATREF set_expression 的 set_expression 参数中用来指示在将 set_expression分配给 SETATREF 中的 _引用_ 参数之前应先计算该参数。  
  
## <a name="syntax"></a>语法

SETATREFEVAL (** *expr* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _expr_ <br/> |必需  <br/> |**变化** <br/> | 一个表达式，在 SETATREF 函数将 set_expression重定向到  _另_ 一个单元格时计算。  <br/> |
   
## <a name="remarks"></a>备注

将 SETATREF set_expression 的 *set_expression* 参数分配给引用的单元格时，Microsoft Visio 默认情况下会将set_expression作为表达式写入该单元格。 但是，如果 *set_expression* 参数的任何部分由 SETATREFEVAL 函数包装，Visio 将计算表达式，在解析 SETATREF 表达式之前，将 SETATREFEVAL 函数替换为其结果。 
  
## <a name="example"></a>示例

有关示例，请参阅 [SETATREF](setatref-function.md) 函数。 
  

