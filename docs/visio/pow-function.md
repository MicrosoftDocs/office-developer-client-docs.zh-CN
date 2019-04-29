---
title: POW 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251483
localization_priority: Normal
ms.assetid: c6519c55-5f98-ed0d-95b1-5443d0d23c0b
description: 返回一个按指数幂增加的数字。
ms.openlocfilehash: 7a1102aa13f54d7e323247b83af3732ebb63acf4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406309"
---
# <a name="pow-function"></a>POW 函数

返回一个按指数幂增加的数字。
  
## <a name="syntax"></a>语法

POW (* * *number* * *, * **指数** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要计算其指数次幂的数字。  <br/> |
| _exponent_ <br/> |必需  <br/> |**Number** <br/> |指数。  <br/> |
   
## <a name="remarks"></a>说明

_number_和_指数_都不能为非整数, 也可以是负数。 如果_number_不是0而_指数_为 0, 则此函数返回1。 如果_number_为0而_指数_为负, 则此函数返回0.0。 如果_number_和_指数_均为 0, 或者_number_为负值且_指数_不是整数, 则此函数返回0.0。 如果_number_和_指数_均为负, 则此函数将返回-1 #IND。 
  
## <a name="example"></a>示例

POW (5, 2) 
  
返回 25。 
  

