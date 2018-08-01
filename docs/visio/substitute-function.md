---
title: SUBSTITUTE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60115
localization_priority: Normal
ms.assetid: 4a27663a-9d37-2ac4-5856-edeb0880f16e
description: 用不同的文本字符串替换文本字符串的一部分。
ms.openlocfilehash: 2c33d8aafbd68054ac39d14bb4fb3cf857fb367e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781462"
---
# <a name="substitute-function"></a>SUBSTITUTE 函数

用不同的文本字符串替换文本字符串的一部分。 
  
## <a name="syntax"></a>语法

 替代 (* **文本** *，* * *old_text* * *，* * *new_text* * * [，* * *start_num* * *] [，* * *ignore_case_opt* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**字符串** <br/> | 要替换其字符的文本或对包含要替换其字符的文本的单元格的引用。  <br/> |
| _old_text_ <br/> |必需  <br/> |**字符串** <br/> | 要替换的文本。 
  <br/> |
| _new_text_ <br/> |必需  <br/> |**字符串** <br/> | 您想要用于替换_old_text_的文本。  <br/> |
| _start_num_opt_ <br/> |可选  <br/> |**Numeric** <br/> |指定要替换 old_text 的哪个匹配项。  <br/> |
| _ignore_case_opt_ <br/> |可选  <br/> |**Boolean** <br/> |如果区分大小写，则其值为 FALSE；否则为 TRUE。默认值为 FALSE。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>说明

 如果指定_start_num_opt_，替换仅的_old_text_中的匹配项。 否则，将每一处的_old_text_中_的文本_更改为_new_text。_
  
如果要替换文本字符串中的特定文本，请使用 SUBSTITUTE 函数。如果要替换在文本字符串中的特定位置出现的文本，请使用 REPLACE 函数。
  
## <a name="example"></a>示例

SUBSTITUTE ("1 January 2003", "January", "JAN") 
  
返回“1 JAN 2003”。 
  
SUBSTITUTE ("1 January 2003","january","JAN") 
  
返回“1 January 2003”。不会进行任何更改，因为文本搜索区分大小写。 
  

