---
title: STnefProblem
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.STnefProblem
api_type:
- COM
ms.assetid: 3fe651b7-0ddf-42fd-8277-9224505be1a8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8595cdb411e68f2aed3ac063b2b81965e9b4d975
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778893"
---
# <a name="stnefproblem"></a>STnefProblem

  
  
**适用于**： Outlook 
  
包含有关编码或解码传输中性封装格式 (TNEF) 流的过程中发生的属性或特性的处理问题的信息。
  
|||
|:-----|:-----|
|头文件：  <br/> |Tnef.h  <br/> |
   
```cpp
typedef struct _STnefProblem
{
  ULONG ulComponent;
  ULONG ulAttribute;
  ULONG ulPropTag;
  SCODE scode;
} STnefProblem;

```

## <a name="members"></a>Members

 **ulComponent**
  
> 处理出现此问题的类型。 如果在消息处理过程中出现此问题， **ulComponent**成员设置为零。 如果附件处理期间出现此问题， **ulComponent**设置等于相应的附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 值。
    
 **ulAttribute**
  
> 与属性关联的属性指示由**ulPropTag**成员中，或者 TNEF 处理问题出现时，当解码封装阻止，下列值之一： 
    
 _attMAPIProps_
  
> 消息级别
    
 _attAttachment_
  
> 附件级别
    
 **ulPropTag**
  
> 属性标记的问题的原因 TNEF 处理，除时解码封装块中，设置为零的案例**ulPropTag**时出现问题的属性。 
    
 **scode**
  
> 错误值，该值指示处理过程中遇到的问题。
    
## <a name="remarks"></a>说明

如果属性或属性的处理过程中未生成**STnefProblem**结构，应用程序可以继续处理属性或属性的成功假定下。 解码封装块的过程中出现问题时，发生此事件唯一的例外。 在这种情况下，解码阻止到相应的组件已停止，解码继续使用在另一个组件。 
  
## <a name="see-also"></a>另请参阅



[STnefProblemArray](stnefproblemarray.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)


[MAPI 结构](mapi-structures.md)

