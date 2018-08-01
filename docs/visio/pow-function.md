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
ms.openlocfilehash: 48870c679251a666a5756b2b684d262fe059eee0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780970"
---
# <a name="pow-function"></a>POW 函数

返回一个按指数幂增加的数字。
  
## <a name="syntax"></a>语法

POW (* **数量** *，* **指数** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**编号** <br/> |要计算其指数次幂的数字。  <br/> |
| _exponent_ <br/> |必需  <br/> |**编号** <br/> |指数。  <br/> |
   
## <a name="remarks"></a>注解

_数字_和_指数_可能非整数，它们可能为负值。 如果_number_不 0 和_指数_为 0，则此函数返回 1。 如果_数字_为 0，并且_指数_为负数，则此函数返回 0.0。 如果_数字_和_指数_0，或者如果_number_为负数和_指数_不是整数，此函数返回 0.0。 如果_数字_和_指数_为负，此函数返回-1。 #IND. 
  
## <a name="example"></a>示例

POW(5,2) 
  
返回 25。 
  

