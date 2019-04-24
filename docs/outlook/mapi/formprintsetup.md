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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327284"
---
# <a name="formprintsetup"></a>FORMPRINTSETUP

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍 form 对象的打印设置信息。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
   
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

## <a name="members"></a>成员

 **ulFlags**
  
> 用于控制字符串类型的标志的位掩码。 可以使用以下标志:
    
MAPI_UNICODE 
  
> 字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 **hDevmode**
  
> 打印机模式的句柄。
    
 **hDevnames**
  
> 打印机路径的句柄。
    
 **ulFirstPageNumber**
  
> 要打印的第一页的页码。
    
 **ulFPrintAttachments**
  
> 指示是否要打印附件的标志。 如果有要打印的附件, **ulFPrintAttachments**成员将设置为1。 如果没有要打印的附件, 则将其设置为0。 
    
## <a name="remarks"></a>注解

**FORMPRINTSETUP**结构用于描述表单对象的打印设置信息。 [IMAPIViewContext:: GetPrintSetup](imapiviewcontext-getprintsetup.md)的实现将填充**FORMPRINTSETUP**结构, 并将其返回到**GetPrintSetup**的_lppFormPrintSetup_输出参数的内容中。
  
如果在**GetPrintSetup**的_ulFlags_参数中传递了 MAPI_UNICODE 标志, 则由**hDevmode**和**hDevnames**成员引用的字符串应采用 UNICODE 格式。 否则, 字符串应为 ANSI 格式。 
  
实现**IMAPIViewContext**的表单查看器必须使用 MAPI 分配器函数[MAPIAllocateBuffer](mapiallocatebuffer.md)分配**FORMPRINTSETUP**结构, 但分配各个成员, **hDevMode**和**hDevNames**,使用 Windows 函数[GlobalAlloc](https://go.microsoft.com/fwlink/?LinkId=132110)。 内存的释放以类似的方式处理。 必须使用 Windows 函数[GlobalFree](https://go.microsoft.com/fwlink/?LinkId=132108)释放**hDevMode**和**hDevNames**成员, 而必须使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放**FORMPRINTSETUP**结构。 
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)


[MAPI 结构](mapi-structures.md)

