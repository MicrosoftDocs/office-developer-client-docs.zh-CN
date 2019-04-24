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
ms.openlocfilehash: fc12ab30ec9c509e2f126931bee837f518e96f3a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346821"
---
# <a name="substitute-function"></a>SUBSTITUTE 函数

用不同的文本字符串替换文本字符串的一部分。 
  
## <a name="syntax"></a>语法

 替换 (* * *text* * *, * * *old_text* * *, * * *new_text* * * [, * * *start_num* * *] [, * * *ignore_case_opt* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _text_ <br/> |必需  <br/> |**String** <br/> | 要替换其字符的文本或对包含要替换其字符的文本的单元格的引用。  <br/> |
| _old_text_ <br/> |必需  <br/> |**String** <br/> | 要替换的文本。  <br/> |
| _new_text_ <br/> |必需  <br/> |**String** <br/> | 要用于替换_old_text_的文本。  <br/> |
| _start_num_opt_ <br/> |可选  <br/> |**Numeric** <br/> |指定要替换的 old_text 的匹配项。  <br/> |
| _ignore_case_opt_ <br/> |可选  <br/> |**Boolean** <br/> |如果区分大小写，则其值为 FALSE；否则为 TRUE。 默认值为 FALSE。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

 如果指定_start_num_opt_, 则仅替换_old_text_的匹配项。 否则,_文本_中_old_text_的每个匹配项都将更改为_new_text。_
  
如果要替换文本字符串中的特定文本，请使用 SUBSTITUTE 函数。如果要替换在文本字符串中的特定位置出现的文本，请使用 REPLACE 函数。
  
## <a name="example"></a>示例

SUBSTITUTE ("1 January 2003", "January", "JAN") 
  
返回“1 JAN 2003”。 
  
SUBSTITUTE ("1 January 2003","january","JAN") 
  
返回“1 January 2003”。不会进行任何更改，因为文本搜索区分大小写。 
  

