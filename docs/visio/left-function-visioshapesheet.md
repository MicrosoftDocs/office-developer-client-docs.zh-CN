---
title: LEFT 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1021757
localization_priority: Normal
ms.assetid: 0c2f6e06-b772-2006-ec7b-8695d097f146
description: 根据指定的字符数, 返回文本字符串中最左侧的字符或字符。
ms.openlocfilehash: aa4141cfc53bd41a6d58e8bc666b18a06fc80245
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309462"
---
# <a name="left-function-visioshapesheet"></a>LEFT 函数 (VisioShapeSheet)

根据指定的字符数, 返回文本字符串中最左侧的字符或字符。
  
## <a name="syntax"></a>语法

LEFT (* * *text* * *, [, * * *num_chars_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> |包含要提取的字符的文本字符串。  <br/> |
| _num_chars_opt_ <br/> |可选  <br/> |**Numeric** <br/> |要提取的字符数。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

_num_chars_opt_的值必须大于或等于零 (0)。 
  
如果_num_chars_opt_大于文本的长度, 则 LEFT 将返回所有文本。 如果省略_num_chars_opt_ , 则假定其为1。 
  
## <a name="example"></a>示例

LEFT ("January 1, 2004", 3) 
  
返回值“Jan”。 
  

