---
title: 强制发送通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9c7d6605-73ee-468c-981b-e0853106c9ba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 54eaf9e67da1b520896122c937508a90700a0b84
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433281"
---
# <a name="forcing-a-notification"></a>强制发送通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当服务提供商使用 [IMAPISupport ： IUnknown](imapisupportiunknown.md) 方法进行通知时，MAPI 使用隐藏窗口及其对应的窗口过程传递通知。 对于每个接收通知的进程，MAPI 将一条特殊消息张贴到隐藏窗口中。 此消息使用 MAPIDEFS.H 中定义的常量 **szMAPINotificationMsg** 命名。 
  
当隐藏窗口的窗口过程处理 **szMAPINotificationMsg** 消息时，您将收到这些通知。 若要确保通知已送达，必须等待并调度此 **szMAPINotificationMsg** 消息。 实现实现此目的的逻辑可以相当简单，但 MAPI 提供了一个进入 MAPI DLL 的入口点，称为 [HrDispatchNotifications，](hrdispatchnotifications.md) 使处理更加简单。 按 **如下所示调用 HrDispatchNotifications** 以在客户端中接收通知： 
  
```cpp
HRESULT hr = HrDispatchNotifications(0);
 
```


