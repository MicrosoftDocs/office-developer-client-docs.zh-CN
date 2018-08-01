---
title: LEFT 的函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1021757
localization_priority: Normal
ms.assetid: 0c2f6e06-b772-2006-ec7b-8695d097f146
description: 文本字符串，根据您指定的字符数中返回的最左侧的字符。
ms.openlocfilehash: 4e8deb3098ce6d217dcce0cae23d07ed723d9fb8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780555"
---
# <a name="left-function-visioshapesheet"></a>LEFT 的函数 (VisioShapeSheet)

文本字符串，根据您指定的字符数中返回的最左侧的字符。
  
## <a name="syntax"></a>语法

左 (* **文本** *，[，* * *num_chars_opt* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**字符串** <br/> |包含要提取的字符的文本字符串。  <br/> |
| _num_chars_opt_ <br/> |可选  <br/> |**Numeric** <br/> |要提取的字符数。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>说明

_Num_chars_opt_的值必须大于或等于零 (0)。 
  
如果_num_chars_opt_大于 text 的长度，LEFT 返回的所有文本。 如果省略_num_chars_opt_ ，则假定为 1。 
  
## <a name="example"></a>示例

LEFT ("January 1, 2004", 3) 
  
返回值“Jan”。 
  

