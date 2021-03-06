---
title: MODULUS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251465
localization_priority: Normal
ms.assetid: cb6326a5-1bf8-b6a3-5c0d-d38c071353a5
description: 返回由 (除) 数时结果的余数模数。
ms.openlocfilehash: f6b713b1b3a9d2afa85f49de9d451642a00d8dad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429269"
---
# <a name="modulus-function"></a>MODULUS 函数

返回由 (除) 数时结果的余数模数。
  
## <a name="syntax"></a>语法

MODULUS (** *number* **， ** *divisor* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |被除数。  <br/> |
| _divisor_ <br/> |必需  <br/> |**Number** <br/> |除数。  <br/> |
   
### <a name="return-value"></a>返回值

帐号
  
## <a name="remarks"></a>备注

结果与除数具有相同的符号。如果除数为 0，则将返回 #DIV/0! 错误。 
  
在绝大多数情况下应使用 MODULUS 函数，而不使用 MOD 函数。 
  
## <a name="example-1"></a>示例 1

MODULUS(5, 1.4)
  
返回 0.8。
  
## <a name="example-2"></a>示例 2

MODULUS(5, -1.4)
  
返回 -0.6。
  
## <a name="example-3"></a>示例 3

MODULUS(-5, 1.4)
  
返回 0.6。
  
## <a name="example-4"></a>示例 4

MODULUS(-5, -1.4)
  
返回 -0.8。
  

