---
title: IPSTOVERRIDEREQRegisterTrustedPSTOverrideHandler
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDEREQ.RegisterTrustedPSTOverrideHandler
api_type:
- COM
ms.assetid: 4a73c77c-7e32-4302-bffe-a1ea13574731
description: '上次修改时间: 2013 年2月24日'
ms.openlocfilehash: acc0986dd80b549b0cb2b941a6937d47a4a959fe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279533"
---
# <a name="ipstoverridereqregistertrustedpstoverridehandler"></a>IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动个人文件夹 (.pst) 文件的解锁过程。
  
```cpp
HRESULT RegisterTrustedPSTOverrideHandler (
  LPCWSTR pwzDllPath, 
  LPVOID pvClientData
); 

```

## <a name="parameters"></a>参数

 _pwzDllPath_
  
> 实时指向第三方动态链接库 (DLL) 的路径的指针。
    
 _pvClientData_
  
> 实时指向客户端数据的指针, 该数据将由 PST 提供程序传递给 DLL 的 HrTrustedPSTOverrideHandlerCallback 函数的后续调用。 DLL 可能会使用此客户端数据来帮助验证是否应解锁 PST。
    
## <a name="return-value"></a>返回值

S_OK
  
> 函数调用成功。
    
## <a name="remarks"></a>注解

必须使用数字证书对 wzDllPath 参数所指定的 DLL 进行签名。 DLL 还必须导出具有以下签名的函数。
  
```
extern "C" HRESULT __cdecl HrTrustedPSTOverrideHandlerCallback(IMsgStore *pmstore, IUnknown *pOverride, LPVOID pvClientData)
```

将使用指向 PST 的 IMsgStore 对象的指针、指向实现 IPSTOVERRIDE1 接口的 IUnknown 对象的指针以及指向最初通过 pvClientData 提供的数据的指针调用此函数。
  
有关详细信息, 请参阅[如何实现 PST 替代处理程序以绕过 Outlook 2007 中的 pstdisablegrow 可策略](https://support.microsoft.com/kb/956070)。
  
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)
  
[IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

