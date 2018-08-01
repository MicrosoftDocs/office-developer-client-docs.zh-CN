---
title: RIGHT 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027314
localization_priority: Normal
ms.assetid: 910f0297-d588-2048-f308-03f3c2389bba
description: 文本字符串，根据您指定的字符数中返回的最后一个字符。
ms.openlocfilehash: e35cc4918809d5f134f9519c01cb3c93407258e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781101"
---
# <a name="right-function-visioshapesheet"></a>RIGHT 函数 (VisioShapeSheet)

文本字符串，根据您指定的字符数中返回的最后一个字符。
  
## <a name="syntax"></a>语法

右 (* **文本** * [，* * *num_chars_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**字符串** <br/> | 包含要提取的字符的文本字符串。  <br/> |
| _num_chars_opt_ <br/> |可选  <br/> |**编号** <br/> |要提取的字符数。默认值为 1。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>说明

_Num_chars_opt_的值必须大于或等于零 (0)。 
  
如果_num_chars_opt_大于 text 的长度，RIGHT 返回的所有文本。 如果省略_num_chars_opt_ ，则假定为 1。 
  
## <a name="example"></a>示例

RIGHT ("January 1, 2004", 4) 
  
返回值 2004。 
  

