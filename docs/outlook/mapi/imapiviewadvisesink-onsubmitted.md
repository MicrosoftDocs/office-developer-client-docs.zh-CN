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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ebde06d0d22320ecb5edb633cf8d04aaeec2a841
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433981"
---
# <a name="imapiviewadvisesinkonsubmitted"></a>IMAPIViewAdviseSink::OnSubmitted

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知表单查看器当前邮件已提交到 MAPI 后台处理程序。
  
```cpp
HRESULT OnSubmitted( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
## <a name="remarks"></a>备注

表单对象在调用 [IMAPIMessageSite：：SubmitMessage](imapimessagesite-submitmessage.md)成功后调用 **IMAPIViewAdviseSink：：OnSubmitted** 方法。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

调用 **OnSubmitted** 后，可以继续假定邮件已更新。 更新窗口以反映已发生的任何更改。 
  
有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::SubmitMessage](imapimessagesite-submitmessage.md)
  
[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

