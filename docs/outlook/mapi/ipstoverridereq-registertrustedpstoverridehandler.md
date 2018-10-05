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
description: 上次修改时间： 2013 年 2 月 24 日
ms.openlocfilehash: acc0986dd80b549b0cb2b941a6937d47a4a959fe
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393871"
---
# <a name="ipstoverridereqregistertrustedpstoverridehandler"></a>IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动个人文件夹 (.pst) 文件的解除过程。
  
```cpp
HRESULT RegisterTrustedPSTOverrideHandler (
  LPCWSTR pwzDllPath, 
  LPVOID pvClientData
); 

```

## <a name="parameters"></a>参数

 _pwzDllPath_
  
> [in]一个指向第三方动态链接库 (DLL) 的路径。
    
 _pvClientData_
  
> [in]一个指向客户端数据，将传入随后调用 DLL 的 HrTrustedPSTOverrideHandlerCallback 函数太平洋标准时间提供程序。 此客户端数据可能由 DLL，用于帮助验证 PST 是否应解除锁定。
    
## <a name="return-value"></a>返回值

S_OK
  
> 函数调用成功。
    
## <a name="remarks"></a>说明

必须使用数字证书签名 wzDllPath 参数指定的 DLL。 DLL 必须还导出带以下签名的函数。
  
```
extern "C" HRESULT __cdecl HrTrustedPSTOverrideHandlerCallback(IMsgStore *pmstore, IUnknown *pOverride, LPVOID pvClientData)
```

与指向 PST 的 IMsgStore 对象的、 指向实现 IPSTOVERRIDE1 接口，IUnknown 对象的指针和指向通过 pvClientData 最初提供数据的指针，将调用此函数。
  
有关详细信息，请参阅[如何实现 PST 重写处理程序，以绕过 Outlook 2007 中的 PSTDisableGrow 策略](https://support.microsoft.com/kb/956070)。
  
## <a name="see-also"></a>另请参阅



[IPSTOVERRIDE1 : IUnknown](ipstoverride1iunknown.md)
  
[IPSTOVERRIDEREQ : IUnknown](ipstoverridereqiunknown.md)

