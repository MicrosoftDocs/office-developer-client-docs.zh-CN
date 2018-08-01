---
title: 替换函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60108
localization_priority: Normal
ms.assetid: 70c9fc1d-6e7b-479f-effd-0d4bc8ae0f72
description: 根据指定的字符数，使用其他文本字符串替换某文本字符串的一部分。
ms.openlocfilehash: 4112339d772248ac033674808d97c3f9c55b6f0a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781061"
---
# <a name="replace-function-visioshapesheet"></a>替换函数 (VisioShapeSheet)

根据指定的字符数，将文本字符串的部分用其他文本字符串替换。
  
## <a name="syntax"></a>语法

替换 (* * *old_text* * *，* * *start_num* * *，* * *num_chars* * *，* * *new_text* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _old_text_ <br/> |必需  <br/> |**字符串** <br/> |要替换其中的一些字符的文本。  <br/> |
| _start_num_ <br/> |必需  <br/> |**编号** <br/> |要用_new_text_替换的_old_text_中字符的位置。 在字符串中的第一个字符是位置 1。  <br/> |
| _num_chars_ <br/> |必需  <br/> |**编号** <br/> |要替换的_old_text_中的字符数  <br/> |
| _new_text_ <br/> |必需  <br/> |**字符串** <br/> |将替换_old_text_中的字符的文本。  <br/> |
   
### <a name="return-value"></a>返回值

字符串
  
## <a name="remarks"></a>注解

要替换出现在文本字符串中的特定位置的文本时，请使用 REPLACE 函数。如果想要替换文本字符串中的特定文本，则请使用 SUBSTITUTE 函数。
  
## <a name="example"></a>示例

REPLACE ("01/03/2002",9,2,"03") 
  
返回 01/03/2003。 
  

