---
title: 强制通知
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
# <a name="forcing-a-notification"></a>强制通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当服务提供程序使用[IMAPISupport: IUnknown](imapisupportiunknown.md)方法进行通知时, MAPI 将使用隐藏窗口及其相应的窗口过程传递通知。 对于每个接收通知的进程, MAPI 都会向隐藏窗口发布一条特殊消息。 此消息使用 mapidefs.h 中定义的常量**szMAPINotificationMsg**进行命名。水平. 
  
当隐藏窗口的窗口过程处理**szMAPINotificationMsg**消息时, 您会收到这些通知。 若要确保传递通知, 需要等待并调度此**szMAPINotificationMsg**消息。 实现此操作的逻辑只是很简单, 但 mapi 提供了名为[HrDispatchNotifications](hrdispatchnotifications.md)的 MAPI DLL 的入口点, 以便更简单地进行处理。 按如下所示调用**HrDispatchNotifications**以在客户端中接收通知: 
  
```cpp
HRESULT hr = HrDispatchNotifications(0);
 
```


