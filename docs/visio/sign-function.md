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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420652"
---
# <a name="sign-function"></a>SIGN 函数

返回一个表示数字符号的值。 
  
## <a name="syntax"></a>语法

SIGN (** *number* **， ** *fuzz* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Numeric** <br/> | 要确定其符号的数字。  <br/> |
| _fuzz_ <br/> |可选  <br/> |**Numeric** <br/> |指定数字接近零达到何种程度时才必须被视为等于零。  <br/> |
   
### <a name="return-value"></a>返回值

Numeric
  
## <a name="remarks"></a>备注

如果 number 为正数，  _则_ SIGN 函数返回 1;如果  _number_ 为零，则返回 0;如果 number 为负，  _则返回_ -1。 
  
指定  _模糊值_ 有助于在计算几乎为零时避免浮点舍入错误。 如果不指定模糊值，Visio  1E-9 (0.0000000001) 。 当您要缩放绘图或进行精确比较时，最好提供不同的值。 
  
## <a name="example-1"></a>示例 1

SIGN (-5) 
  
返回 -1。
  
## <a name="example-2"></a>示例 2

SIGN (0) 
  
返回 0。
  
## <a name="example-3"></a>示例 3

SIGN (0.00000000001) 
  
返回 0。
  
## <a name="example-4"></a>示例 4

SIGN (0.00000000001，0) 
  
返回 1。
  

