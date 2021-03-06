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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a58e723113f70c10b5c8468f5bdd0d8d9014bd2c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425125"
---
# <a name="imapiviewcontextgetprintsetup"></a>IMAPIViewContext::GetPrintSetup

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索当前打印信息。
  
```cpp
HRESULT GetPrintSetup(
ULONG ulFlags,
LPFORMPRINTSETUP FAR * lppFormPrintSetup
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制返回的字符串类型的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _lppFormPrintSetup_
  
> [out]指向指向包含打印信息的结构的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索打印信息。
    
## <a name="remarks"></a>备注

Form 对象调用 **IMAPIViewContext：：GetPrintSetup** 方法，以在尝试打印当前邮件之前检索有关打印机设置的信息。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

使用 Win32 函数 **GlobalAlloc** 分配 [FORMPRINTSETUP](formprintsetup.md)结构的 **hDevMode** 和 **hDevName** 成员。
  
## <a name="notes-to-callers"></a>给调用方的说明

如果您希望 _lppFormPrintSetup_ 参数指向的 **FORMPRINTSETUP** 结构的 **hDevMode** 和 **hDevName** 成员为 Unicode 字符串，则将 _ulFlags_ 设置为 MAPI_UNICODE。 否则 **，GetPrintSetup** 将返回 ANSI 格式的这些字符串。 
  
通过调用 Win32 函数 **GlobalFree** 释放 **FORMPRINTSETUP** 结构的 **hDevMode** 和 **hDevName** 成员。 通过调用 [MAPIFreeBuffer](mapifreebuffer.md)释放整个 **FORMPRINTSETUP** 结构。 
  
## <a name="see-also"></a>另请参阅



[FORMPRINTSETUP](formprintsetup.md)
  
[IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md)

