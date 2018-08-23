---
title: IMAPIViewContextGetPrintSetup
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetPrintSetup
api_type:
- COM
ms.assetid: eaf3bafb-975d-42c8-99ea-7f9ef9c934ba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 63e3eca4e91e560a28d57f05250264d7e0592142
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587255"
---
# <a name="imapiviewcontextgetprintsetup"></a>IMAPIViewContext::GetPrintSetup

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检索当前打印的信息。
  
```cpp
HRESULT GetPrintSetup(
ULONG ulFlags,
LPFORMPRINTSETUP FAR * lppFormPrintSetup
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制返回的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
 _lppFormPrintSetup_
  
> [输出]一个包含打印信息结构为指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索打印的信息。
    
## <a name="remarks"></a>注解

表单对象调用**IMAPIViewContext::GetPrintSetup**方法检索有关的打印机设置打印当前消息在尝试之前的信息。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

分配**hDevMode**和**hDevName**使用 Win32 函数**GlobalAlloc** [FORMPRINTSETUP](formprintsetup.md)结构的成员。
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您希望**hDevMode** **FORMPRINTSETUP**结构的**hDevName**成员所指的_lppFormPrintSetup_参数设置为 Unicode 字符串，设置为 MAPI_UNICODE _ulFlags_ 。 否则， **GetPrintSetup**将以 ANSI 格式返回这些字符串。 
  
通过调用 Win32 函数**GlobalFree**释放**hDevMode**和**hDevName** **FORMPRINTSETUP**结构的成员。 通过调用[MAPIFreeBuffer](mapifreebuffer.md)释放整个**FORMPRINTSETUP**结构。 
  
## <a name="see-also"></a>另请参阅



[FORMPRINTSETUP](formprintsetup.md)
  
[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)

