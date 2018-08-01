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
ms.openlocfilehash: 3c480c420753b2da6c57b3961589d5c2e2e8022a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776544"
---
# <a name="notifkey"></a>NOTIFKEY

  
  
**适用于**： Outlook 
  
唯一标识通知接收器、 advise 源和 MAPI 之间的连接。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapispi.h  <br/> |
   
```cpp
typedef struct
{
  ULONG cb;
  BYTE ab[MAPI_DIM];
} NOTIFKEY, FAR *LPNOTIFKEY;

```

## <a name="members"></a>Members

 **cb**
  
> **Ab**成员中的字节数。 
    
 **ab**
  
> 描述通知密钥的字节数组。
    
## <a name="remarks"></a>说明

[IMAPISupport](imapisupportiunknown.md)的[Subscribe](imapisupport-subscribe.md)和[Notify](imapisupport-notify.md)方法使用**NOTIFKEY**结构生成适当的通知接收器有关适合 advise 源通知。 
  
服务提供商生成通知密钥时调用其**Advise**方法，他们希望将呼叫**Subscribe**来处理通知注册和后续发送的通知。 通知键可 advise 源的项标识符，也可以是任何其他标识的项目，如常量。 例如，消息存储提供程序可能使用的文件夹的路径作为通知键。 
  
跨多个进程情况下，通知键应起作用。 
  
通知密钥的作用域要求类似于那些长期的项标识符。 但是，与条目标识符，不同通知密钥必须二进制比较。 通常情况下，通知键包括由到对象后跟唯一其他特定于提供程序的信息的服务提供程序定义的**GUID**值。 
  
有关**NOTIFKEY**结构管理使用的讨论 advise 接收器生成通知的对象之间的连接，请参阅[支持事件通知](supporting-event-notification.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 结构](mapi-structures.md)

