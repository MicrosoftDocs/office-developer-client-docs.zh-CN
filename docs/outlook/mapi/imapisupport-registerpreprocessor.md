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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 219c15fc00490983e970e4533f927cf4d91916b6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775658"
---
# <a name="imapisupportregisterpreprocessor"></a>IMAPISupport::RegisterPreprocessor

  
  
**适用于**： Outlook 
  
注册传输提供程序的预处理器函数 （符合[PreprocessMessage](preprocessmessage.md)原型函数）。 
  
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
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含预处理器的函数处理的标识符。 _LpMuid_参数可以是 NULL。 
    
 _lpszAdrType_
  
> [in]函数如传真、 SMTP 或 X500 的操作，一个指向邮件的地址类型。 _LpszAdrType_参数可以是 NULL。 
    
 _lpszDLLName_
  
> [in]一个指向包含预处理器函数的入口点的动态链接库 (DLL) 的名称。
    
 _lpszPreprocess_
  
> [in]一个指向预处理器函数的名称。 _LpszPreprocess_参数可以是 NULL。 
    
 _lpszRemovePreprocessInfo_
  
> [in]一个指向删除预处理器信息 （符合[RemovePreprocessInfo](removepreprocessinfo.md)原型函数） 函数的名称。 _LpszRemovePreprocessInfo_参数可以是 NULL。 
    
 _ulFlags_
  
> 保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 预处理器函数已成功注册。
    
## <a name="remarks"></a>说明

对于传输提供程序支持对象仅实现**IMAPISupport::RegisterPreprocessor**方法。 传输提供程序调用**RegisterPreprocessor**注册预处理器函数 （符合[PreprocessMessage](preprocessmessage.md)原型的函数）。 MAPI 后台处理程序可调用它之前，必须注册预处理器函数。 
  
_LpszPreprocess_、 _lpszRemovePreprocessInfo_和_lpszDLLName_参数应指向可以与呼叫允许预处理器的 DLL 的 Win32 **GetProcAddress**函数结合使用的字符串正确调用入口点。 
  
## <a name="notes-to-callers"></a>给调用方的说明

调用 preprocessors 是特定于传输提供程序的顺序。 这意味着您的提供商之前的另一个传输提供程序是能够处理一条消息，如果您预处理器函数将不会调用该邮件。 只对将处理的消息，将调用您预处理器函数。
  
您可以编写预处理器函数来处理存储在[MAPIUID](mapiuid.md)结构或类型的地址中的任一一个特定的标识符。 如果指定这两个**MAPIUID**结构_lpMuid_参数和_lpszAdrType_参数中的地址类型，您的函数将调用**MAPIUID**或地址类型相匹配的邮件收件人。 如果_lpszAdrType_为非 NULL _lpMuid_为 NULL，将只为收件人的地址所指的_lpszAdrType_的类型相匹配的调用您函数。 _LpMuid_非空并且_lpszAdrType_为 NULL，如果您的函数将调用的匹配**MAPIUID**，无论其地址类型的收件人。 如果二者均为空，函数调用的所有收件人的邮件。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[PreprocessMessage](preprocessmessage.md)
  
[RemovePreprocessInfo](removepreprocessinfo.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

