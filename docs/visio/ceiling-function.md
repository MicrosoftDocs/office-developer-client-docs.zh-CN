---
title: CEILING 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251405
localization_priority: Normal
ms.assetid: 1a8d6d48-7ae3-5483-28d2-5b1706088a53
description: 将数字从 0（零）后舍入到 multiple 的下一个实例。如果未指定 multiple，会将数字从 0 后舍入到下一个整数。
ms.openlocfilehash: 449f17d1b68c116cccb2635723a3f6277d0ac2a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404125"
---
# <a name="ceiling-function"></a>CEILING 函数

将数字从 0 舍入 (零) 多个 的下一  _个实例_。 如果  _未指定 multiple，_ 则数字从 0 舍入到下一个整数。 
  
## <a name="syntax"></a>语法

CEILING (** *number* **， ** *multiple* ** )  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _number_ <br/> |必需  <br/> |**Number** <br/> |要舍入的数字。  <br/> |
| _multiple_ <br/> |必需  <br/> |**Number** <br/> |要舍入到的倍数。  <br/> |
   
## <a name="remarks"></a>备注

 _Number_ 和  _multiple_ 必须具有相同的符号，否则#NUM！ 错误。 如果 _数字或__多个_ 不能转换为值，则#VALUE！ 错误。 如果  _number_ 或  _multiple_ 为 0，则结果为 0。 
  
## <a name="example-1"></a>示例 1

CEILING (3.7) 
  
返回 4
  
## <a name="example-2"></a>示例 2

CEILING (-3.7) 
  
返回 -4
  
## <a name="example-3"></a>示例 3

CEILING (3.7， 0.25) 
  
返回 3.75
  

