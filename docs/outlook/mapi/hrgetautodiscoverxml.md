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
  
返回一个可扩展标记语言 (XML) 流, 该流表示从 Microsoft Exchange 2007 服务器的自动发现服务中检索的信息。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者:  <br/> |olmapi32  <br/> |
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
  
> 实时要为其检索自动发现信息的帐户的以 null 结尾的简单邮件传输协议 (SMTP) 电子邮件地址。
    
 _pwzPassword_
  
> 实时由_pwzAddress_指定的帐户的可选密码。 请注意, 如果_pwzAddress_指定的帐户不需要密码, 传递任何密码将不起作用。 
    
 _hCancelEvent_
  
> 实时取消设置的 Win32 事件句柄, 它是可选的, 可用于取消操作。 若要取消该操作, 请设置事件并将事件句柄作为_hCancelEvent_传递。如果您不想取消该操作, 则传递**null** 。 请注意, 传递不代表事件句柄的值不起作用, 并且该函数将忽略它。 
    
 _ulFlags_
  
> 实时不使用此参数。 它必须为0。
    
 _ppXmlStream_
  
> 排除指向包含自动发现 XML 的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象的指针。 如果自动发现操作失败, 则返回**null** 。 完成[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象后, 必须释放该对象。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 函数调用成功。
    
E_INVALIDARG 
  
-  _pwzAddress_为**null**或不是有效的 SMTP 地址, 或者_ppXmlStream_是指向[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象的**null**指针。 
    
MAPI_E_NOT_FOUND 
  
- 客户端计算机未连接到网络, 客户端计算机未连接到 Microsoft exchange 2007 服务器, _pwzAddress_不是 Exchange 2007 服务器上的帐户, 或者_pwzAddress_是不支持 exchange 的帐户。自动发现服务。 
    
MAPI_E_USER_CANCEL 
  
- 已将事件句柄传递给_hCancelEvent_以取消该操作。 
    
STRSAFE_E_INSUFFICIENT_BUFFER
  
- 传递给_pwzAddress_或_pwzPassword_的值太长, 因此它会溢出大小为256字节的内部缓冲区。 
    

