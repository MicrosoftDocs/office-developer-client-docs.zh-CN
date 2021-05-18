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

POW (** *number* **， ** *exponent* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要计算其指数次幂的数字。  <br/> |
| _exponent_ <br/> |必需  <br/> |**Number** <br/> |指数。  <br/> |
   
## <a name="remarks"></a>备注

_number_ 和 _exponent_ 可能是非整数，并且可能是负数。 如果  _number_ 不为 0，  _指数_ 为 0，则此函数返回 1。 如果  _number_ 为  _0，指数为_ 负数，则此函数返回 0.0。 如果  _number 和_  _exponent_ 都为 0，或者  _number_ 为负数且  _exponent_ 不是整数，则此函数返回 0.0。 如果  _number 和_  _exponent_ 都是负数，则此函数返回 -1.#IND。 
  
## <a name="example"></a>示例

POW (5，2)  
  
返回 25。 
  

