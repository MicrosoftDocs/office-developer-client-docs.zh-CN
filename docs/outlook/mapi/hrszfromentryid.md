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
ms.openlocfilehash: 1b957c02f331038ee9104f01806720d2f8e0b542
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775183"
---
# <a name="hrszfromentryid"></a>HrSzFromEntryID

  
  
**适用于**： Outlook 
  
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
  
## <a name="remarks"></a>说明

[HrEntryIDFromSz](hrentryidfromsz.md)和**HrSzFromEntryID**函数提供的字符串和项标识符的二进制格式之间的转换。 使用 MAPI，应使用二进制数据结构。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrSzFromEntryID**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的 ASCII 字符串分配内存。 
  

