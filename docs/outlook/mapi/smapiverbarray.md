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
ms.openlocfilehash: 1767c86cb5390572b95530060f2295034ed35f43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778841"
---
# <a name="smapiverbarray"></a>SMAPIVerbArray

  
  
**适用于**： Outlook 
  
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
    
## <a name="remarks"></a>说明

**SMAPIVerbArray**结构作为中[IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md)方法的参数传递。 
  
## <a name="see-also"></a>另请参阅



[SMAPIVerb](smapiverb.md)


[MAPI 结构](mapi-structures.md)

