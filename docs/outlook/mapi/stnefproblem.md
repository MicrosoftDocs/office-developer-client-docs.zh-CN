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
ms.openlocfilehash: 19d20a3fb06f6a0a0671ba4bfd938da314001778
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435178"
---
# <a name="stnefproblem"></a>STnefProblem

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关 TNEF 流中传输中性封装格式或传输中性封装格式的编码或解码过程中 (或) 问题的信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef.h  <br/> |
   
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
  
> 出现问题的处理类型。 如果在邮件处理过程中出现问题 **，ulComponent** 成员将设置为零。 如果在附件处理过程中出现问题，则 **ulComponent** 设置为等于相应的附件的 PR_ATTACH_NUM  ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 值。
    
 **ulAttribute**
  
> 与 **ulPropTag** 成员指示的属性关联的属性，或者当解码封装块时 TNEF 处理出现问题时，为下列值之一： 
    
 _attMAPIProps_
  
> 邮件级别
    
 _attAttachment_
  
> 附件级别
    
 **ulPropTag**
  
> 导致 TNEF 处理问题的属性的属性标记，除非解码封装块时出现问题，在这种情况下 **ulPropTag** 设置为零。 
    
 **scode**
  
> 指示处理过程中遇到的问题的错误值。
    
## <a name="remarks"></a>备注

如果在处理属性或属性期间未生成 **STnefProblem** 结构，则应用程序可以在该属性或属性处理成功的假设下继续。 唯一的异常是在解码封装块期间出现问题时发生。 在这种情况下，将停止与块对应的组件解码，并且在另一个组件中继续解码。 
  
## <a name="see-also"></a>另请参阅



[STnefProblemArray](stnefproblemarray.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)


[MAPI 结构](mapi-structures.md)

