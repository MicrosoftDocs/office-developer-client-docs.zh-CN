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
ms.openlocfilehash: 7cba5dce60ce15ddb12776d619143849298aac9f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357475"
---
# <a name="smapiverbarray"></a>SMAPIVerbArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含描述 MAPI 谓词的[SMAPIVerb](smapiverb.md)结构的数组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|相关宏:  <br/> |[CbMAPIVerbArray](cbmapiverbarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cMAPIVerb;
  SMAPIVerb aMAPIVerb[MAPI_DIM];
} SMAPIVerbArray, FAR * LPMAPIVERBARRAY;

```

## <a name="members"></a>Members

 **cForms**
  
> 数组中的谓词的计数。
    
 **aFormInfo**
  
> MAPI 谓词数组。
    
## <a name="remarks"></a>注解

**SMAPIVerbArray**结构作为参数传递到[IMAPIFormInfo:: CalcVerbSet](imapiforminfo-calcverbset.md)方法中。 
  
## <a name="see-also"></a>另请参阅



[SMAPIVerb](smapiverb.md)


[MAPI 结构](mapi-structures.md)

