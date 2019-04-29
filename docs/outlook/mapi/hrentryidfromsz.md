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
ms.openlocfilehash: ac59aeb3d650c0fbeb5bcdb580e0401cbab58ee6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437726"
---
# <a name="hrentryidfromsz"></a>HrEntryIDFromSz

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从其 ASCII 编码重新创建条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT HrEntryIDFromSz(
  LPSTR sz,
  ULONG FAR * pcb,
  LPENTRYID FAR * ppentry
);
```

## <a name="parameters"></a>参数

 _sz_
  
> 实时指向从中创建条目标识符的 ASCII 字符串的指针。 
    
 _pcb_
  
> 排除指向由_ppentry_参数指向的条目标识符的大小 (以字节为单位) 的指针。 
    
 _ppentry_
  
> 排除指向指向包含新条目标识符的返回[ENTRYID](entryid.md)结构的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 重新创建成功。
    
MAPI_E_INVALID_ENTRYID
  
> 条目 ID 无效。
    
## <a name="remarks"></a>说明

**HrEntryIDFromSz**和[HrSzFromEntryID](hrszfromentryid.md)函数提供条目标识符的字符串和二进制格式之间的转换。 
  
## <a name="notes-to-callers"></a>给调用方的说明

**HrEntryIDFromSz**函数使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为 ASCII 字符串分配内存。 
  

