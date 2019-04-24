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
ms.openlocfilehash: 40d65af25d89774c1bdf7b235cf653dbb61dd1c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322496"
---
# <a name="find-function"></a>FIND 函数

查找包含在另一个文本字符串中的一个文本字符串，并返回您查找的文本字符串相对于其在所处文本字符串中位置的起始位置。
  
## <a name="syntax"></a>语法

FIND (* * *find_text* * *, * * *within_text* * *, [* * *start_num* * *], [* * *ignore_case* * *]) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _find_text_ <br/> |必需  <br/> |**String** <br/> |要查找的文本字符串。  <br/> |
| _format_ <br/> |必需  <br/> |**String** <br/> |包含要查找的文本的文本字符串。  <br/> |
| _start_num_ <br/> |可选  <br/> |**Number** <br/> |从该处开始搜索的字符。 _within_text_中的第一个字符是1。 如果缺少_start_num_ , 则假定其为1。  <br/> |
| _ignore_case_ <br/> |可选  <br/> |**Boolean** <br/> |默认情况下，FIND 函数区分大小写。 如果希望 FIND 函数忽略大小写，请将此参数设置为 TRUE。  <br/> |
   
### <a name="return-value"></a>返回值

帐号
  
## <a name="remarks"></a>注解

如果找到多个匹配结果，FIND 函数将返回第一个匹配结果在字符串中的起始位置。 _find_text_参数不考虑将任何字符设为通配符。 
  
如果_find_text_:
  
-  为空 (""), 则查找匹配搜索字符串中的第一个字符 (即编号为_start_num_或1的字符)。 
    
- 不显示在_within_text_中, FIND 将返回 #VALUE! 。 
    
如果_start_num_:
  
- 不大于零 (0)，FIND 将返回 #VALUE! 错误值。 
    
- 大于_within_text_的长度, 请 FINDreturns #VALUE! 错误值。 
    
## <a name="example"></a>示例

FIND ("2003","January 1, 2003") 
  
返回 12。 
  

