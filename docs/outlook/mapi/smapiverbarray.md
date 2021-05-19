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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433911"
---
# <a name="smapiverbarray"></a>SMAPIVerbArray

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一组描述 MAPI 动词的 [SMAPIVerb](smapiverb.md) 结构。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|相关宏：  <br/> |[CbMAPIVerbArray](cbmapiverbarray.md) <br/> |
   
```cpp
typedef struct
{
  ULONG cMAPIVerb;
  SMAPIVerb aMAPIVerb[MAPI_DIM];
} SMAPIVerbArray, FAR * LPMAPIVERBARRAY;

```

## <a name="members"></a>Members

 **cForms**
  
> 数组中的动词计数。
    
 **aFormInfo**
  
> MAPI 动词数组。
    
## <a name="remarks"></a>备注

**SMAPIVerbArray** 结构作为 [IMAPIFormInfo：：CalcVerbSet](imapiforminfo-calcverbset.md)方法中的参数传递。 
  
## <a name="see-also"></a>另请参阅



[SMAPIVerb](smapiverb.md)


[MAPI 结构](mapi-structures.md)

