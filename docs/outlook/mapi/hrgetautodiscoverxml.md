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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: da466fc9add8cbc385014782f31749d3b6522da9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775158"
---
# <a name="hrgetautodiscoverxml"></a>HrGetAutoDiscoverXML

  
  
**适用于**： Outlook 
  
返回一个值，该值代表从 Microsoft Exchange 2007 服务器的自动发现服务检索信息的可扩展标记语言 (XML) 流。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |olmapi32.dll  <br/> |
|调用：  <br/> |客户端  <br/> |
|通过实现：  <br/> |Outlook  <br/> |
   
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
  
> [in]Null 结尾简单邮件传输协议 (SMTP) 电子邮件地址要检索的自动发现信息的帐户。
    
 _pwzPassword_
  
> [in]指定_pwzAddress_帐户可选密码。 请注意，是否_pwzAddress_指定的帐户不需要密码，传递任何密码没有任何效果。 
    
 _hCancelEvent_
  
> [in]未设置的 Win32 事件句柄的是可选的可使用以取消操作。 若要取消操作，设置事件，并为_hCancelEvent_; 传递事件句柄如果您不希望以取消操作，则传递**null** 。 将值传递不代表事件句柄的注释不起作用，并忽略函数。 
    
 _ulFlags_
  
> [in]不使用此参数。 它必须是 0。
    
 _ppXmlStream_
  
> [输出]指向包含自动发现 XML 的[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象的指针。 如果自动发现操作失败，则返回**null** 。 在与之完成时，您必须释放[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 成功函数调用。
    
E_INVALIDARG 
  
-  _pwzAddress_为**null**或不是有效的 SMTP 地址，或_ppXmlStream_是**null**指向[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象。 
    
MAPI_E_NOT_FOUND 
  
- 客户端计算机未连接到网络、 客户端计算机未连接到 Microsoft Exchange 2007 服务器、 _pwzAddress_不是在 Exchange 2007 服务器上，帐户或_pwzAddress_是不支持 Exchange 帐户自动发现服务。 
    
MAPI_E_USER_CANCEL 
  
- 事件句柄已传递到_hCancelEvent_以取消操作。 
    
STRSAFE_E_INSUFFICIENT_BUFFER
  
- 传递给_pwzAddress_或_pwzPassword_值过长，以便它超出的内部缓冲区的大小 256 字节。 
    

