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
  
注册传输提供程序的预处理器函数 (符合[PreprocessMessage](preprocessmessage.md)原型的函数)。 
  
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
  
> 实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含预处理器函数所处理的标识符。 _lpMuid_参数可以为 NULL。 
    
 _lpszAdrType_
  
> 实时指向函数所运行的邮件的地址类型的指针, 例如传真、SMTP 或 X500。 _lpszAdrType_参数可以为 NULL。 
    
 _lpszDLLName_
  
> 实时指向包含预处理器函数入口点的动态链接库 (DLL) 名称的指针。
    
 _lpszPreprocess_
  
> 实时指向预处理器函数名称的指针。 _lpszPreprocess_参数可以为 NULL。 
    
 _lpszRemovePreprocessInfo_
  
> 实时指向删除预处理器信息的函数名称的指针 (符合[RemovePreprocessInfo](removepreprocessinfo.md)原型的函数)。 _lpszRemovePreprocessInfo_参数可以为 NULL。 
    
 _ulFlags_
  
> 保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功注册预处理器函数。
    
## <a name="remarks"></a>说明

仅为传输提供程序支持对象实现了**IMAPISupport:: RegisterPreprocessor**方法。 传输提供程序调用**RegisterPreprocessor**以注册预处理器函数 (符合[PreprocessMessage](preprocessmessage.md)原型的函数)。 预处理器函数必须先注册, 然后 MAPI 后台处理程序才能调用它。 
  
_lpszPreprocess_、 _lpszRemovePreprocessInfo_和_lpszDLLName_参数都应指向可与 Win32 **GetProcAddress**函数的调用结合使用的字符串, 从而允许预处理器 DLL要正确调用的入口点。 
  
## <a name="notes-to-callers"></a>给调用方的说明

对 preprocessors 的调用特定于传输提供程序的顺序。 这意味着, 如果您的提供程序前面的另一个传输提供程序能够处理邮件, 则不会为该邮件调用预处理程序函数。 将仅调用您要处理的邮件的预处理器函数。
  
您可以编写预处理器函数来处理存储在[MAPIUID](mapiuid.md)结构或地址类型中的特定标识符。 如果在_lpMuid_参数中指定了**MAPIUID**结构, 并在_lpszAdrType_参数中指定了地址类型, 则将为与**MAPIUID**或地址类型匹配的邮件收件人调用函数。 如果_lpMuid_为 NULL 且_lpszAdrType_为非 NULL, 则仅对其地址与_lpszAdrType_指向的类型相匹配的收件人调用函数。 如果_lpMuid_为非 null, 并且_lpszAdrType_为 null, 则将为匹配**MAPIUID**的收件人调用您的函数, 而不考虑其地址类型。 如果两者都为 NULL, 则为邮件的所有收件人调用函数。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[PreprocessMessage](preprocessmessage.md)
  
[RemovePreprocessInfo](removepreprocessinfo.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

