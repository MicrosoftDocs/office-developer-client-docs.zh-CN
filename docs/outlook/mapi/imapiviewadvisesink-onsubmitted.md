---
title: IMAPIViewAdviseSinkOnSubmitted
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnSubmitted
api_type:
- COM
ms.assetid: a2401662-1ddc-40d8-a5a7-ceca24442bd4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2aa1aca2816b8f0e148d35d1fcec761f621a2239
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579443"
---
# <a name="imapiviewadvisesinkonsubmitted"></a>IMAPIViewAdviseSink::OnSubmitted

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通知表单查看器的当前消息，已提交到 MAPI 后台处理程序。
  
```cpp
HRESULT OnSubmitted( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>注解

Form 对象调用**IMAPIViewAdviseSink::OnSubmitted**方法对[IMAPIMessageSite::SubmitMessage](imapimessagesite-submitmessage.md)的调用返回了成功之后。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

调用**OnSubmitted**后，您可以继续在假设邮件已更新。 更新您的 windows，以反映发生任何更改。 
  
有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::SubmitMessage](imapimessagesite-submitmessage.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

