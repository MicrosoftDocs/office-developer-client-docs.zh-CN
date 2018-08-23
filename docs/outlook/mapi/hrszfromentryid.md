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
ms.openlocfilehash: 366208b8288aeb61bf1bb78f2c9f10b400a3dc26
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567592"
---
# <a name="hrszfromentryid"></a>HrSzFromEntryID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
编码为 ASCII 字符串的项标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
HrSzFromEntryID(
  ULONG cb,
  LPENTRYID pentry,
  LPSTR FAR * psz
);
```

## <a name="parameters"></a>参数

 _cb_
  
> [in]大小，以字节为单位_pentry_参数指向的项标识符。 
    
 _pentry_
  
> [in]指向[ENTRYID](entryid.md)结构，其中包含要编码的项标识符的指针。 
    
 _psz_
  
> [输出]指向返回 ASCII 字符串。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

[HrEntryIDFromSz](hrentryidfromsz.md)和**HrSzFromEntryID**函数提供的字符串和项标识符的二进制格式之间的转换。 使用 MAPI，应使用二进制数据结构。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrSzFromEntryID**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的 ASCII 字符串分配内存。 
  

