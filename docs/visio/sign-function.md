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
ms.openlocfilehash: 34bbbab17de94b0a8c95b4b0bfd3829a06dc7e70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357454"
---
# <a name="sign-function"></a>SIGN 函数

返回一个表示数字符号的值。 
  
## <a name="syntax"></a>语法

SIGN (* * *number* * *, * * *fuzz* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Numeric** <br/> | 要确定其符号的数字。  <br/> |
| _fuzz_ <br/> |可选  <br/> |**Numeric** <br/> |指定数字接近零达到何种程度时才必须被视为等于零。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>注解

如果 number 为正数, 则__ SIGN 函数返回 1; 如果__ number 为零, 则返回 0; 如果_number_为负, 则返回-1。 
  
Specifyin 当计算几乎为零时, _fuzz_值有助于避免浮点 roundoff 错误。 如果不指定_fuzz_值, Visio 将使用 1e-9 (0.000000001)。 当您要缩放绘图或进行精确比较时，最好提供不同的值。 
  
## <a name="example-1"></a>示例 1

符号 (-5)
  
返回 -1。
  
## <a name="example-2"></a>示例 2

符号 (0)
  
返回 0。
  
## <a name="example-3"></a>示例 3

符号 (0.00000000001)
  
返回 0。
  
## <a name="example-4"></a>示例 4

SIGN (0.00000000001, 0)
  
返回 1。
  

