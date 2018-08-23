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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 761228a01e0dc778b962c62436e872ff20d72088
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586310"
---
# <a name="ixplogontransportlogoff"></a>IXPLogon::TransportLogoff

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启动注销过程。 
  
```cpp
HRESULT TransportLogoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。 如果返回 S_OK 之外的任何，提供程序被注销。
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon::TransportLogoff**方法终止传输提供程序会话的特定用户。 调用**TransportLogoff**之前, MAPI 后台处理程序放弃[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法中传递该会话的支持邮件的地址类型有关的任何数据。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

传输提供程序应准备随时接受**TransportLogoff**调用。 如果消息的过程中，提供程序应停止发送进程。 
  
传输提供程序应释放分配其当前会话的所有资源。 如果它具有与[MAPIAllocateBuffer](mapiallocatebuffer.md)函数该会话的分配任何内存，它应使用[MAPIFreeBuffer](mapifreebuffer.md)函数释放内存。 此时可以安全地释放由传输提供程序以满足对[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法调用分配任何内存。 
  
通常，在完成**TransportLogoff**呼叫，提供程序应首先使其登录对象无效通过调用[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)方法，然后释放其支持对象。 因为 MAPI 后台处理程序发布支持对象时，还可以解除提供商对象本身， **TransportLogoff**提供程序的实现应最后一发行版支持对象。 
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

