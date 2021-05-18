---
title: IMAPISupportRegisterPreprocessor
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.RegisterPreprocessor
api_type:
- COM
ms.assetid: 9b5659ab-2b49-41ab-92ce-ca343e35d670
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 58215de6cc4e9e68386f8f017839752acc6e1753
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404895"
---
# <a name="imapisupportregisterpreprocessor"></a>IMAPISupport::RegisterPreprocessor

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在符合 [PreprocessMessage](preprocessmessage.md) 原型模型 (注册传输提供程序的预处理器) 。 
  
```cpp
HRESULT RegisterPreprocessor(
LPMAPIUID lpMuid,
LPSTR lpszAdrType,
LPSTR lpszDLLName,
LPSTR lpszPreprocess,
LPSTR lpszRemovePreprocessInfo,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpMuid_
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，该结构包含预处理器函数处理的标识符。 _lpMuid_ 参数可以是 NULL。 
    
 _lpszAdrType_
  
> [in]指向函数所操作的邮件的地址类型的指针，例如 FAX、SMTP 或 X500。 _lpszAdrType_ 参数可以是 NULL。 
    
 _lpszDLLName_
  
> [in]指向动态链接库名称的指针 (DLL) ，其中包含预处理器函数的入口点。
    
 _lpszPreprocess_
  
> [in]指向预处理器函数名称的指针。 _lpszPreprocess 参数_ 可以是 NULL。 
    
 _lpszRemovePreprocessInfo_
  
> [in]指向函数名称的指针，该名称将删除符合 [RemovePreprocessInfo](removepreprocessinfo.md) 原型 (函数的预处理器) 。 _lpszRemovePreprocessInfo_ 参数可以是 NULL。 
    
 _ulFlags_
  
> 保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 预处理器函数已成功注册。
    
## <a name="remarks"></a>备注

**IMAPISupport：：RegisterPreprocessor** 方法仅为传输提供程序支持对象实现。 传输提供程序调用 **RegisterPreprocessor** 以在符合 [PreprocessMessage](preprocessmessage.md) 原型 (的函数中注册预处理器) 。 必须先注册预处理器函数，MAPI 后台处理程序才能调用它。 
  
_lpszPreprocess、lpszRemovePreprocessInfo_ 和 _lpszDLLName_ 参数都应指向可与 Win32 **GetProcAddress** 函数调用结合使用的字符串，从而允许正确调用预处理器的 DLL 入口点。  
  
## <a name="notes-to-callers"></a>给调用方的说明

对预处理器的调用特定于传输提供程序顺序。 这意味着，如果提供程序之前的另一个传输提供程序能够处理邮件，将不会为邮件调用预处理器函数。 将仅对将处理的邮件调用预处理器函数。
  
你可以编写预处理器函数来处理 [MAPIUID](mapiuid.md) 结构中存储的特定标识符或地址类型。 如果在 _lpMuid_ 参数中同时指定 **MAPIUID** 结构，在 _lpszAdrType_ 参数中指定地址类型，将调用与 **MAPIUID** 或地址类型匹配的邮件收件人的函数。 如果  _lpMuid_ 为 NULL 且  _lpszAdrType_ 为非 NULL，则仅对地址与  _lpszAdrType_ 指向的类型匹配的收件人调用函数。 如果  _lpMuid_ 为非 NULL 且  _lpszAdrType_ 为 NULL，则无论收件人的地址类型如何，都将为 **匹配 MAPIUID** 的收件人调用函数。 如果两者都是 NULL，则为邮件的所有收件人调用函数。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[PreprocessMessage](preprocessmessage.md)
  
[RemovePreprocessInfo](removepreprocessinfo.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

