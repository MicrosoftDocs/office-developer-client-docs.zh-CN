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
  
描述窗体对象的打印设置信息。 
  
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

## <a name="members"></a>成员

 **ulFlags**
  
> 控制字符串类型的标志的位掩码。 可以使用以下标志：
    
MAPI_UNICODE 
  
> 字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 **hDevmode**
  
> 打印机模式的句柄。
    
 **hDevnames**
  
> 打印机路径的句柄。
    
 **ulFirstPageNumber**
  
> 要打印的第一页的页码。
    
 **ulFPrintAttachments**
  
> 指示是否有附件要打印的标志。 如果存在要打印的附件，则 **ulFPrintAttachments** 成员设置为 1。 如果没有附件要打印，则设置为 0。 
    
## <a name="remarks"></a>备注

**FORMPRINTSETUP** 结构用于描述窗体对象的打印设置信息。 [IMAPIViewContext：：GetPrintSetup](imapiviewcontext-getprintsetup.md)的实现填充 **FORMPRINTSETUP** 结构，并返回在 **GetPrintSetup**_的 lppFormPrintSetup_ 输出参数的内容中。
  
如果 MAPI_UNICODE 标志在 **GetPrintSetup** 的 _ulFlags_ 参数中传递，**则 hDevmode** 和 **hDevnames** 成员引用的字符串应为 Unicode 格式。 否则，字符串应为 ANSI 格式。 
  
实现 **IMAPIViewContext** 的表单查看器必须使用 MAPI 分配程序函数 [MAPIAllocateBuffer](mapiallocatebuffer.md)分配 **FORMPRINTSETUP** 结构，但使用 Windows 函数 [GlobalAlloc](https://go.microsoft.com/fwlink/?LinkId=132110)分配单个成员 **hDevMode** 和 **hDevNames。** 内存释放的处理方式类似。 **hDevMode** 和 **hDevNames** 成员必须使用 Windows 函数 [GlobalFree](https://go.microsoft.com/fwlink/?LinkId=132108)释放，而 **FORMPRINTSETUP** 结构必须使用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放。 
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::GetPrintSetup](imapiviewcontext-getprintsetup.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)


[MAPI 结构](mapi-structures.md)

