---
title: SMAPIFormProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormProp
api_type:
- COM
ms.assetid: 80f1c2e0-3567-4b16-86cb-d5e6ac95c2ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 968f9e1dad3a233b31f0ce29d3ce935b1257948c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416697"
---
# <a name="smapiformprop"></a>SMAPIFormProp

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述用于窗体的命名属性。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
   
```cpp
typedef struct _SMAPIFormProp
{
  ULONG ulFlags;
  ULONG nPropType;
  MAPINAMEID nmid;
  LPSTR pszDisplayName;
  FORMPROPSPECIALTYPE nSpecialType;
  union
  {
    struct
    {
      MAPINAMEID nmidIdx;
      ULONG cfpevAvailable;
      LPMAPIFORMPROPENUMVAL pfpevAvailable;
    } s1;
  } u;
} SMAPIFormProp, FAR * LPMAPIFORMPROP;

```

## <a name="members"></a>成员

 **ulFlags**
  
> 用于区分 **SMAPIFormProp** 结构中字符串格式的标志。 可以设置以下标志： 
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 **nPropType**
  
> 命名属性的类型，最显著的单词设置为零。 
    
 **nmid**
  
> 命名属性的名称，其中包括标识属性集的 **GUID** 结构以及表示接口标识符和表单名称的数字或字符串值。 
    
 **pszDisplayName**
  
> 指向显示名称属性的指针。
    
 **nSpecialType**
  
> 用于描述 **u** 成员中包含的数据类型的值。 可能的值如下所示： 
    
FPST_VANILLA 
  
> **u** 成员不包含枚举。 
    
FPST_ENUM_PROP 
  
> **u** 成员包含描述枚举的结构。 
    
 **u**
  
> 描述命名属性的名称和编号之间的关联。 通过使用某些属性 **，u** 成员为空。 对于其他属性，它以由以下成员组成的结构表示： 
    
 **nmidIdx**
  
> 包含命名属性的属性集和标识符的 [MAPINAMEID](mapinameid.md) 结构。 
    
 **cfpevAvailable**
  
> **pfpevAvailable** 成员指向的数组中的 [SMAPIFormPropEnumVal](smapiformpropenumval.md)结构计数。 
    
 **pfpevAvailable**
  
> 指向 **SMAPIFormPropEnumVal** 结构的数组的指针，其中每个结构包含命名属性的值。 
    
## <a name="remarks"></a>备注

**SMAPIFormProp** 结构包含有关用作 [IMAPIFormInfo](imapiforminfoimapiprop.md)接口定义的一部分的表单属性的信息;**nSpecialType** 包含一个适用于属于 **SMAPIFormProp** 的 **u** 联合的标记。
  
## <a name="see-also"></a>另请参阅



[MAPINAMEID](mapinameid.md)
  
[SMAPIFormPropEnumVal](smapiformpropenumval.md)


[MAPI 结构](mapi-structures.md)

