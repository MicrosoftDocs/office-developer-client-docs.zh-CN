---
title: SIGN 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251497
localization_priority: Normal
ms.assetid: fdc032c2-d0bd-1592-de3f-33c478d066ee
description: 返回一个表示数字符号的值。
ms.openlocfilehash: 5f812dc4313e15df5d66a919707e7cdbb79f94b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781370"
---
# <a name="sign-function"></a>SIGN 函数

返回一个表示数字符号的值。 
  
## <a name="syntax"></a>语法

登录 (* **数量** *，* **模糊化** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Numeric** <br/> | 要确定其符号的数字。  <br/> |
| _模糊化_ <br/> |可选  <br/> |**Numeric** <br/> |指定数字接近零达到何种程度时才必须被视为等于零。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>注解

如果_number_为正数，SIGN 函数返回 1、 0 如果_number_是零，则为-1，如果_number_为负数。 
  
Specifyin_模糊化_值有助于避免浮点舍入错误时计算结果近似为零。 如果不指定_模糊化_值，Visio 会使用 1E-9 (0.000000001)。 您可能想要扩展绘图或时所需的确切比较提供不同的值。 
  
## <a name="example-1"></a>示例 1

SIGN(-5)
  
返回 -1。
  
## <a name="example-2"></a>示例 2

SIGN(0)
  
返回 0。
  
## <a name="example-3"></a>示例 3

SIGN(0.00000000001)
  
返回 0。
  
## <a name="example-4"></a>示例 4

SIGN(0.00000000001,0)
  
返回 1。
  

