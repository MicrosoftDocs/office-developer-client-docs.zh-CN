---
title: FIND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60101
localization_priority: Normal
ms.assetid: c827ecd4-5593-6d4f-2746-d13b02b098fe
description: 查找包含在另一个文本字符串中的一个文本字符串，并返回您查找的文本字符串相对于其在所处文本字符串中位置的起始位置。
ms.openlocfilehash: e29e8e89418f0162cae0ec9904c2205218e799ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780282"
---
# <a name="find-function"></a>FIND 函数

查找包含在另一个文本字符串中的一个文本字符串，并返回您查找的文本字符串相对于其在所处文本字符串中位置的起始位置。
  
## <a name="syntax"></a>语法

查找 (* * *find_text* * *，* * *within_text* * *，[* * *start_num* * *]，[* * *ignore_case* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _find_text_ <br/> |必需  <br/> |**字符串** <br/> |要查找的文本字符串。  <br/> |
| _format_ <br/> |必需  <br/> |**字符串** <br/> |包含要查找的文本的文本字符串。  <br/> |
| _start_num_ <br/> |可选  <br/> |**编号** <br/> |开始搜索的字符。 在_within_text_中的第一个字符是 1。 如果_start_num_不存在，假定为 1。  <br/> |
| _ignore_case_ <br/> |可选  <br/> |**Boolean** <br/> |默认情况下，FIND 函数区分大小写。如果希望 FIND 函数忽略大小写，请将此参数设置为 TRUE。  <br/> |
   
### <a name="return-value"></a>返回值

Number
  
## <a name="remarks"></a>说明

如果找到了多个匹配，则 FIND 函数返回字符串中的第一个匹配的起始位置。 _Find_text_参数不考虑为通配符任意字符。 
  
如果_find_text_:
  
-  为空 ("")，FIND 将匹配搜索字符串中的第一个字符 （即，字符编号_为 start_num_或 1）。 
    
- 不会显示在_within_text_中，查找返回 #VALUE ！ 错误值。 
    
如果_start_num_:
  
- 不大于零 (0)，FIND 将返回 #VALUE! 错误值。 
    
- 大于_within_text_，find 将返回 #VALUE 的长度 ！ 错误值。 
    
## <a name="example"></a>示例

FIND ("2003","January 1, 2003") 
  
返回 12。 
  

