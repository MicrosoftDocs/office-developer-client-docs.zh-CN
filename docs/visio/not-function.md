---
title: NOT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251469
localization_priority: Normal
ms.assetid: 65873b32-2406-7c33-8e68-802461f467b2
description: 如果在 logicalexpression 为 false，则，返回 TRUE (1)。 否则，将返回 FALSE (0)。
ms.openlocfilehash: e2359aaab18469cd4f272f71aca8d899a12b2120
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780796"
---
# <a name="not-function"></a>NOT 函数

如果_在 logicalexpression_为 false，则，返回 TRUE (1)。 否则，将返回 FALSE (0)。 
  
## <a name="syntax"></a>语法

不 (* **在 logicalexpression* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _在 logicalexpression_ <br/> |必需  <br/> |**字符串** <br/> |要计算的逻辑表达式。  <br/> |
   
### <a name="return-value"></a>返回值

Boolean
  
## <a name="example"></a>示例

不 (高度\>0.75 中) 
  
如果高度小于或等于 0.75 英寸，则返回 1。如果高度大于 0.75 英寸，则返回 0。 
  

