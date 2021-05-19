---
title: HrGetAutoDiscoverXML
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrGetAutoDiscoverXML
api_type:
- COM
ms.assetid: 03691187-7c65-620b-576f-6ebe62a80830
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 77f28654ffe0f6f459fde229bb7428f2c39e96c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347801"
---
# <a name="hrgetautodiscoverxml"></a>HrGetAutoDiscoverXML

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回 Extensible Markup Language (XML) stream，该流表示从 Microsoft Exchange 2007 服务器的自动发现服务检索的信息。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |olmapi32.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
HRESULT HrGetAutoDiscoverXML( 
    __in_z const WCHAR *pwzAddress, 
    __in_opt_z const WCHAR *pwzPassword, 
    __in_opt HANDLE hCancelEvent, 
    __in_opt ULONG ulFlags, 
    __out IStream** ppXmlStream); 

```

## <a name="parameters"></a>参数

 _pwzAddress_
  
> [in]以 null 终止的简单邮件传输 (SMTP) 要检索其自动发现信息的帐户的电子邮件地址。
    
 _pwzPassword_
  
> [in]由  _pwzAddress 指定的_ 帐户的可选密码。 请注意，如果  _pwzAddress_ 指定的帐户不需要密码，则传递任何密码都无效。 
    
 _hCancelEvent_
  
> [in]可选的未设置 Win32 事件句柄，可用于取消操作。 若要取消操作，请设置 事件，将事件句柄传递为  _hCancelEvent_;如果 **不想** 取消操作，请传递 null。 请注意，传递不代表事件句柄的值不起作用，函数将忽略该值。 
    
 _ulFlags_
  
> [in]此参数未使用。 它必须是 0。
    
 _ppXmlStream_
  
> [out]指向包含自动发现 XML 的 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 对象的指针。 如果 **自动** 发现操作失败，则返回 null。 完成 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 对象后，必须释放该对象。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 函数调用成功。
    
E_INVALIDARG 
  
-  _pwzAddress_ **为 null** 或不是有效的 SMTP 地址，或者 _ppXmlStream_ 是指向 [IStream 对象的](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)**空** 指针。 
    
MAPI_E_NOT_FOUND 
  
- 客户端计算机未连接到网络、客户端计算机未连接到 Microsoft Exchange 2007 服务器 _、pwzAddress_ 不是 Exchange 2007 服务器的帐户，或者 _pwzAddress_ 是不支持 Exchange 自动发现服务的帐户。 
    
MAPI_E_USER_CANCEL 
  
- 事件句柄已传递到  _hCancelEvent_ 以取消操作。 
    
STRSAFE_E_INSUFFICIENT_BUFFER
  
- 传递给  _pwzAddress_ 或  _pwzPassword_ 的值太长，因此它会溢出大小为 256 字节的内部缓冲区。 
    

