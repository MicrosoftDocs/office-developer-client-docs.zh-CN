---
title: NOTIFKEY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.NOTIFKEY
api_type:
- COM
ms.assetid: 031b7e18-59b2-445c-a747-348fda92f458
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ab1586696a4b72aa9e88545c2069c3f8b5d22d72
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429626"
---
# <a name="notifkey"></a>NOTIFKEY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
唯一标识建议接收器、建议源和 MAPI 之间的连接。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi.h  <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE ab[MAPI_DIM];
} NOTIFKEY, FAR *LPNOTIFKEY;

```

## <a name="members"></a>Members

 **cb**
  
> ab 成员中的 **字节** 数。 
    
 **ab**
  
> 描述通知密钥的字节数组。
    
## <a name="remarks"></a>备注

[IMAPISupport](imapisupportiunknown.md)的 [Subscribe](imapisupport-subscribe.md)和 [Notify](imapisupport-notify.md)方法使用 **NOTIFKEY** 结构向相应的建议接收器生成有关相应建议源的通知。 
  
当调用其 **Advise** 方法并且希望调用 **Subscribe** 以处理通知注册和随后发送通知时，服务提供商将生成通知密钥。 通知键可以是通知源的条目标识符，也可以是任何其他标识项（如常量）。 例如，邮件存储提供程序可能会将文件夹的路径用作其通知键。 
  
通知密钥应跨多个进程工作。 
  
通知项的范围要求类似于长期条目标识符的范围要求。 但是，与条目标识符不同，通知键必须是二进制比较的。 通常，通知键包括由服务提供商定义的 **GUID** 值，后跟对象特有的其他提供程序特定信息。 
  
有关使用 **NOTIFKEY** 结构管理通知接收器与生成通知的对象之间连接的讨论，请参阅S [supporting Event Notification。](supporting-event-notification.md) 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

