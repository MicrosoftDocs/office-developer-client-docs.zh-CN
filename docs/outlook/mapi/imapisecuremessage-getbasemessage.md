---
title: IMAPISecureMessageGetBaseMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISecureMessage.GetBaseMessage
api_type:
- COM
ms.assetid: 573f40c5-e0d2-4281-8c22-10a1ae1f0dee
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d246fc0cfc60d0a2b9ff12ee70eae2366cf9b53a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594836"
---
# <a name="imapisecuremessagegetbasemessage"></a>IMAPISecureMessage::GetBaseMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索基础[IMessage: IMAPIProp](imessageimapiprop.md)这[IMAPISecureMessage: IUnknown](imapisecuremessageiunknown.md)封装。 
  
```cpp
HRESULT GetBaseMessage(
  LPMMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a>参数

 _ppmsg_
  
> [输出]一个安全邮件对象。
    
## <a name="return-value"></a>返回值

S_OK
  
> 呼叫成功或多个预期值返回。
    
## <a name="see-also"></a>另请参阅



[IMAPISecureMessage : IUnknown](imapisecuremessageiunknown.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

