---
title: IMAPIViewAdviseSinkOnNewMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnNewMessage
api_type:
- COM
ms.assetid: 0a2fb371-90ea-41dc-b2ab-051cf790e85a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6a6f8f9d675bee362b4a9f1c5b7fc544fa66d7b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328789"
---
# <a name="imapiviewadvisesinkonnewmessage"></a>IMAPIViewAdviseSink::OnNewMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知表单查看器新的或现有的邮件已在表单中加载。
  
```cpp
HRESULT OnNewMessage( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>注解

当使用[IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md)方法在窗体中加载邮件时, form 对象将调用**IMAPIViewAdviseSink:: OnNewMessage**方法。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

释放指向 form 对象的活动指针, 因为它不再指向您的查看器以前查看的邮件。 
  
有关表单通知的详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIForm : IUnknown](imapiformiunknown.md)
  
[IPersistMessage::InitNew](ipersistmessage-initnew.md)
  
[IPersistMessage::Load](ipersistmessage-load.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

