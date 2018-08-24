---
title: SMAPIVerbArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIVerbArray
api_type:
- COM
ms.assetid: 8736f75c-3e95-42dd-9bc1-2f0bd23c4a02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a2911779e5f9edb8c0bba7c3476a74ce410477c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569461"
---
# <a name="smapiverbarray"></a>SMAPIVerbArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含描述 MAPI 谓词的[SMAPIVerb](smapiverb.md)结构的数组。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|相关的宏：  <br/> |[CbMAPIVerbArray](cbmapiverbarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cMAPIVerb;
  SMAPIVerb aMAPIVerb[MAPI_DIM];
} SMAPIVerbArray, FAR * LPMAPIVERBARRAY;

```

## <a name="members"></a>Members

 **cForms**
  
> 动词数组中的计数。
    
 **aFormInfo**
  
> MAPI 谓词的数组。
    
## <a name="remarks"></a>注解

**SMAPIVerbArray**结构作为中[IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md)方法的参数传递。 
  
## <a name="see-also"></a>另请参阅



[SMAPIVerb](smapiverb.md)


[MAPI 结构](mapi-structures.md)

