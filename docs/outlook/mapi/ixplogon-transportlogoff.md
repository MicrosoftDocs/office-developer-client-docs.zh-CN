---
title: IXPLogonTransportLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.TransportLogoff
api_type:
- COM
ms.assetid: b2b368ce-4486-4f90-985f-59e50ca95229
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 78b4feeca263035b9c90184f10edd294e6cd7b10
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417859"
---
# <a name="ixplogontransportlogoff"></a>IXPLogon::TransportLogoff

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
启动注销过程。 
  
```cpp
HRESULT TransportLogoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。 如果返回 S_OK 之外的任何内容, 则将注销该提供程序。
    
## <a name="remarks"></a>说明

MAPI 后台处理程序调用**IXPLogon:: TransportLogoff**方法, 以终止特定用户的传输提供程序会话。 在调用**TransportLogoff**之前, MAPI 后台处理程序会丢弃有关在[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法中传递的此会话的受支持的邮件地址类型的任何数据。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

传输提供程序应准备好随时接受对**TransportLogoff**的调用。 如果正在处理邮件, 则提供程序应停止发送过程。 
  
传输提供程序应释放为其当前会话分配的所有资源。 如果它已使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数为此会话分配了任何内存, 它应使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放内存。 传输提供程序为满足对[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法的调用而分配的任何内存都可以安全地发布。 
  
通常, 在完成**TransportLogoff**调用之后, 提供程序应首先通过调用[IMAPISupport:: MakeInvalid](imapisupport-makeinvalid.md)方法来使其登录对象失效, 然后释放其支持对象。 提供程序的**TransportLogoff**实现将在最后发布支持对象, 因为在发布支持对象时, MAPI 后台处理程序还可以释放提供程序对象本身。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

