---
title: IF 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251442
localization_priority: Normal
ms.assetid: 66771ad3-0fb3-68ff-81da-d1162d37c05a
description: 如果 logicalexpression 为 TURE，则返回 valueiftrue。否则，将返回 valueiffalse。
ms.openlocfilehash: 55938e8bd78c02badb98f90665c5c26cdd70f3b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780433"
---
# <a name="if-function"></a>IF 函数

如果_在 logicalexpression_为 TRUE，则返回_valueiftrue_ 。 否则，它返回_valueiffalse_。
  
## <a name="syntax"></a>语法

如果 (* **在 logicalexpression* * *，* * *valueiftrue* * *，* * *valueiffalse* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _在 logicalexpression_ <br/> |必需  <br/> |**字符串** <br/> |要计算的表达式。  <br/> |
| _valueiftrue_ <br/> |必需  <br/> |**因情况而异** <br/> |返回_在 logicalexpression_为 true 的值。  <br/> |
| _valueiffalse_ <br/> |必需  <br/> |**因情况而异** <br/> | 返回_在 logicalexpression_为 false 的值。  <br/> |
   
### <a name="return-value"></a>返回值

因情况而异
  
## <a name="example"></a>示例

如果 (高度\>中的 1.25 5、 7)
  
如果形状的高度大于 1.25 英寸，则返回 5。如果形状的高度小于或等于 1.25 英寸，则返回 7。
  

