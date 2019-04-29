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
  
包含有关在编码或解码传输中性封装格式 (TNEF) 流过程中出现的属性或属性处理问题的信息。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef  <br/> |
   
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
  
> 发生问题的处理类型。 如果在邮件处理过程中出现问题, **ulComponent**成员将设置为零。 如果在附件处理过程中出现问题, 则将**ulComponent**设置为等于相应附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 值。
    
 **ulAttribute**
  
> 与**ulPropTag**成员指示的属性相关联的属性, 或者, 如果在解码封装块时出现 TNEF 处理问题, 则为下列值之一: 
    
 _attMAPIProps_
  
> 邮件级别
    
 _attAttachment_
  
> 附件级别
    
 **ulPropTag**
  
> 导致 TNEF 处理问题的属性的属性标记, 但在解码封装块时出现问题, 在此情况下将**ulPropTag**设置为零。 
    
 **scode**
  
> 指示处理过程中遇到的问题的错误值。
    
## <a name="remarks"></a>说明

如果在处理属性或属性的过程中不会生成**STnefProblem**结构, 则在假定该属性或属性的处理成功的情况下, 应用程序可以继续。 仅当在封装块解码过程中出现问题时, 才会发生此异常。 在这种情况下, 将停止对与块相对应的组件进行解码, 并在另一个组件中继续解码。 
  
## <a name="see-also"></a>另请参阅



[STnefProblemArray](stnefproblemarray.md)
  
[PidTagAttachNumber 规范属性](pidtagattachnumber-canonical-property.md)


[MAPI 结构](mapi-structures.md)

