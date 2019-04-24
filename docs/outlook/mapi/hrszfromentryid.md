---
title: HrSzFromEntryID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrSzFromEntryID
api_type:
- COM
ms.assetid: 5e3ed6b2-8eaf-44ab-bc6a-d3faabe84a93
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4020a9161a51994ebe5b7e339d26f7612ad47361
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346415"
---
# <a name="hrszfromentryid"></a>HrSzFromEntryID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将条目标识符编码为 ASCII 字符串。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrSzFromEntryID(
  ULONG cb,
  LPENTRYID pentry,
  LPSTR FAR * psz
);
```

## <a name="parameters"></a>参数

 _cb_
  
> 实时由_pentry_参数指向的条目标识符的大小 (以字节为单位)。 
    
 _pentry_
  
> 实时指向包含要编码的条目标识符的[ENTRYID](entryid.md)结构的指针。 
    
 _psz_
  
> 排除指向返回的 ASCII 字符串的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

[HrEntryIDFromSz](hrentryidfromsz.md)和**HrSzFromEntryID**函数提供条目标识符的字符串和二进制格式之间的转换。 使用 MAPI 时, 应使用二进制数据的结构。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrSzFromEntryID**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为 ASCII 字符串分配内存。 
  

