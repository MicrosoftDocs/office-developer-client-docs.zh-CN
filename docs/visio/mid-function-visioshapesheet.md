---
title: MID 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027310
localization_priority: Normal
ms.assetid: 5041d957-1bd9-4d76-cf43-7b4fcd1e7dec
description: 返回特定的文本字符串，指定，位置开始中的字符数根据您指定的字符数。
ms.openlocfilehash: 96e697211ebf6ea61ddf0b749d8e1259f2a1e53d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780772"
---
# <a name="mid-function-visioshapesheet"></a>MID 函数 (VisioShapeSheet)

返回特定的文本字符串，指定，位置开始中的字符数根据您指定的字符数。
  
## <a name="syntax"></a>语法

MID (* **文本** *，* * *start_num* * *，* * *num_chars* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**字符串** <br/> |包含要提取的字符的文本字符串。  <br/> |
| _start_num_ <br/> |必需  <br/> |**编号** <br/> |要提取的第一个字符的位置。文本字符串中第一个字符处于位置 1。  <br/> |
| _num_chars_ <br/> |必需  <br/> |**编号** <br/> |要返回的字符数。  <br/> |
   
### <a name="return-value"></a>返回值

String
  
## <a name="remarks"></a>注解

如果*start_num:* 
  
- 大于的长度*文本*，MID 将返回""（空文本）。 
    
- 小于长度的*文本*，但*start_num*加上*num_chars*超过*text*的长度，MID 将返回到*文本*末尾的字符。 
    
- 小于 1，MID 将返回 #VALUE! 错误值。 
    
如果*num_chars*为负数，MID 将返回 #VALUE ！。 错误值。 
  
## <a name="example"></a>示例

MID ("SSN 999-99-9999",5,11) 
  
返回 999-99-9999。 
  

