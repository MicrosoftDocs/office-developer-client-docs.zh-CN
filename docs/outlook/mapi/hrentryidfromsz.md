---
title: HrEntryIDFromSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HrEntryIDFromSz
api_type:
- COM
ms.assetid: 14c171ec-0aec-43ab-8be8-e6bc0ce28a58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2b7ef789c80f85f3539ec3bbd0caf4a8adc50f3e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775166"
---
# <a name="hrentryidfromsz"></a>HrEntryIDFromSz

  
  
**适用于**： Outlook 
  
重新创建从其 ASCII 编码的项标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT HrEntryIDFromSz(
  LPSTR sz,
  ULONG FAR * pcb,
  LPENTRYID FAR * ppentry
);
```

## <a name="parameters"></a>参数

 _sz_
  
> [in]指向 ASCII 字符串从中创建的项标识符的指针。 
    
 _pcb_
  
> [输出]指向的大小，以字节为单位_ppentry_参数指向的项标识符的指针。 
    
 _ppentry_
  
> [输出]返回包含新的项标识符的[ENTRYID](entryid.md)结构为指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 重新创建已成功。
    
MAPI_E_INVALID_ENTRYID
  
> 条目 ID 无效。
    
## <a name="remarks"></a>说明

**HrEntryIDFromSz**和[HrSzFromEntryID](hrszfromentryid.md)函数提供的字符串和项标识符的二进制格式之间的转换。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrEntryIDFromSz**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的 ASCII 字符串分配内存。 
  

