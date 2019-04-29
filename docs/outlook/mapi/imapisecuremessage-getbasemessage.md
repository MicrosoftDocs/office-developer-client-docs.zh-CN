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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a2da3f6851e45a70dcd4604396a85430c539a830
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428576"
---
# <a name="imapisecuremessagegetbasemessage"></a>IMAPISecureMessage::GetBaseMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索此[IMAPISecureMessage: IUnknown](imapisecuremessageiunknown.md)封装的基础[IMessage: IMAPIProp](imessageimapiprop.md) 。 
  
```cpp
HRESULT GetBaseMessage(
  LPMMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a>参数

 _ppmsg_
  
> 排除安全邮件对象。
    
## <a name="return-value"></a>返回值

S_OK
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="see-also"></a>另请参阅



[IMAPISecureMessage : IUnknown](imapisecuremessageiunknown.md)
  
[IMessage : IMAPIProp](imessageimapiprop.md)

