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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 73475c5ee4e715796e06642756c05746b271d128
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778815"
---
# <a name="smapiformprop"></a>SMAPIFormProp

  
  
**适用于**： Outlook 
  
描述用于窗体的命名的属性。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
   
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
  
> 用于区分**SMAPIFormProp**结构中的字符串格式的标志。 可以设置以下标记： 
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 的字符串是以 ANSI 格式。
    
 **nPropType**
  
> 命名属性，设置为零的最大单词的类型。 
    
 **nmid**
  
> 包含标识表示接口标识符和窗体名称的属性集和数字或字符串值的**GUID**结构的命名属性的名称。 
    
 **pszDisplayName**
  
> 指向的命名属性的显示名称。
    
 **nSpecialType**
  
> 描述**u**成员中包含的数据类型的值。 可能值如下所示： 
    
FPST_VANILLA 
  
> **U**成员不包含枚举。 
    
FPST_ENUM_PROP 
  
> **U**成员包含描述枚举的结构。 
    
 **u**
  
> 联合描述的名称和数量的命名属性之间的关联。 通过使用一些属性， **u**成员为空。 与其他属性，它表示在结构包含的以下成员： 
    
 **nmidIdx**
  
> 包含的属性集和命名属性标识符的[MAPINAMEID](mapinameid.md)结构。 
    
 **cfpevAvailable**
  
> 由**pfpevAvailable**成员指向[SMAPIFormPropEnumVal](smapiformpropenumval.md)结构数组中的计数。 
    
 **pfpevAvailable**
  
> 指向数组**SMAPIFormPropEnumVal**结构，其中每个保留的命名属性的值。 
    
## <a name="remarks"></a>备注

**SMAPIFormProp**结构包含有关用作[IMAPIFormInfo](imapiforminfoimapiprop.md)接口; 的定义的一部分的窗体属性的信息**nSpecialType**包含适用于**u**联合**SMAPIFormProp**的一部分的标记。
  
## <a name="see-also"></a>另请参阅



[MAPINAMEID](mapinameid.md)
  
[SMAPIFormPropEnumVal](smapiformpropenumval.md)


[MAPI 结构](mapi-structures.md)

