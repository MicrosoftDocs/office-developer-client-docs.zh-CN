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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419602"
---
# <a name="imapiviewadvisesinkonnewmessage"></a>IMAPIViewAdviseSink::OnNewMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知表单查看器已在表单中加载了新邮件或现有邮件。
  
```cpp
HRESULT OnNewMessage( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
## <a name="remarks"></a>备注

只要使用 [IPersistMessage：：InitNew](ipersistmessage-initnew.md)或 [IPersistMessage：：Load](ipersistmessage-load.md)方法在表单中加载邮件，Form 对象就会调用 **IMAPIViewAdviseSink：：OnNewMessage** 方法。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

释放窗体对象的活动指针，因为它不再指向查看者以前查看的消息。 
  
有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIForm : IUnknown](imapiformiunknown.md)
  
[IPersistMessage::InitNew](ipersistmessage-initnew.md)
  
[IPersistMessage::Load](ipersistmessage-load.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

