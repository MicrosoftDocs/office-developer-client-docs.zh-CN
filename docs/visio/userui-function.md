---
title: USERUI 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251511
localization_priority: Normal
ms.assetid: c01dd938-677c-b2ba-8f56-4638e7e988fd
description: 根据状态值计算两个表达式之一。
ms.openlocfilehash: 544bb2b19dc610591afc78c407301098fac9c7c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420344"
---
# <a name="userui-function"></a>USERUI 函数

根据状态 的值计算两个表达式中的一  _个_。
  
## <a name="syntax"></a>语法

USERUI (** *state* **， ** *defaultexpression* **， ** *userexpression* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _state_ <br/> |必需  <br/> |**Boolean** <br/> |确定要计算哪个表达式。  <br/> |
| _defaultexpression_ <br/> |必需  <br/> |**String** <br/> |默认表达式。  <br/> |
| _userexpression_ <br/> |必需  <br/> |**String** <br/> |由用户提供的表达式。  <br/> |
   
## <a name="remarks"></a>备注

如果  _state_ 为 0，则 USERUI 函数将计算  _defaultexpression_。 如果  _state_ 为 1，则计算  _userexpression_。
  
## <a name="example"></a>示例

USERUI (1，如果 (Width \> 6in， 6in， Width) ， Width \* 0.75)  
  
计算表达式 Width \* .075 并返回结果。 
  

