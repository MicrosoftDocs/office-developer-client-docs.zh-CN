---
title: FORMPRINTSETUP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FORMPRINTSETUP
api_type:
- COM
ms.assetid: 6e82fe94-47bd-4a25-b25b-0ab6fe2db274
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c2b9176e21341ef28e6f0bc007757b097a05daee
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386570"
---
# <a name="formprintsetup"></a>FORMPRINTSETUP

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍 form 对象的打印设置信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
   
```cpp
typedef struct
{
  ULONG ulFlags;
  HDEVMODE hDevMode;
  HDEVNAMES hDevNames;
  ULONG ulFirstPageNumber;
  ULONG ulFPrintAttachments;
} FORMPRINTSETUP, FAR * LPFORMPRINTSETUP;

```

## <a name="members"></a>Members

 **ulFlags**
  
> 位掩码的标志，控制字符串的类型。 可以使用以下标记：
    
MAPI_UNICODE 
  
> 字符串是 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 **hDevmode**
  
> 打印机的模式的句柄。
    
 **hDevnames**
  
> 处理到打印机的路径。
    
 **ulFirstPageNumber**
  
> 要打印的第一页的页码。
    
 **ulFPrintAttachments**
  
> 指示是否有要打印的附件的标志。 如果要打印的附件， **ulFPrintAttachments**成员设置为 1。 如果不有任何附件打印，则将其设置为 0。 
    
## <a name="remarks"></a>说明

**FORMPRINTSETUP**结构用于描述 form 对象的打印设置信息。 实现的[IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md)填写**FORMPRINTSETUP**结构，并将其返回**GetPrintSetup** _lppFormPrintSetup_输出参数的内容中。
  
如果**GetPrintSetup**的_ulFlags_参数中传递 MAPI_UNICODE 标志，则引用的**hDevmode**和**hDevnames**成员的字符串应为 Unicode 格式。 否则，字符串应以 ANSI 格式。 
  
实现**IMAPIViewContext**表单查看器必须分配**FORMPRINTSETUP**结构使用 MAPI 分配器函数[MAPIAllocateBuffer](mapiallocatebuffer.md)，但分配各个成员， **hDevMode**和**hDevNames**，与 Windows 函数[GlobalAlloc](https://go.microsoft.com/fwlink/?LinkId=132110)。 同样处理内存的版本。 使用 Windows 函数[GlobalFree](https://go.microsoft.com/fwlink/?LinkId=132108)而必须用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**FORMPRINTSETUP**结构，必须释放的**hDevMode**和**hDevNames**成员。 
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)


[MAPI 结构](mapi-structures.md)

