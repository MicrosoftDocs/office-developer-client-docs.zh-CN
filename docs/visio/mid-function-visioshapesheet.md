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
description: 根据指定的字符数, 从指定的位置开始, 返回文本字符串中的特定数量的字符。
ms.openlocfilehash: 58d5e784e49c8e9fba0bf668626049298783c158
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360660"
---
# <a name="mid-function-visioshapesheet"></a>MID 函数 (VisioShapeSheet)

根据指定的字符数, 从指定的位置开始, 返回文本字符串中的特定数量的字符。
  
## <a name="syntax"></a>语法

MID (* * *text* * *、* * *start_num* * *、* * *num_chars* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> |包含要提取的字符的文本字符串。  <br/> |
| _start_num_ <br/> |必需  <br/> |**Number** <br/> |要提取的第一个字符的位置。 文本字符串中第一个字符处于位置 1。  <br/> |
| _num_chars_ <br/> |必需  <br/> |**Number** <br/> |要返回的字符数。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

如果*start_num*为: 
  
- MID 大于*文本*长度, MID 返回 "" (空文本)。 
    
- 小于*文本*长度, 但*start_num*加*num_chars*超过*文本*的长度, MID 返回*文本*的末尾之前的字符。 
    
- 小于 1，MID 将返回 #VALUE! 错误值。 
    
如果*num_chars*为负值, MID 将返回 #VALUE! 错误值。 
  
## <a name="example"></a>示例

MID ("SSN 999-99-9999",5,11) 
  
返回 999-99-9999。 
  

