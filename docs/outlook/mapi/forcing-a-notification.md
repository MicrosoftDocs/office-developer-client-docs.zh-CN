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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328096"
---
# <a name="forcing-a-notification"></a><span data-ttu-id="8be2c-103">强制通知</span><span class="sxs-lookup"><span data-stu-id="8be2c-103">Forcing a Notification</span></span>

  
  
<span data-ttu-id="8be2c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8be2c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8be2c-105">当服务提供程序使用[IMAPISupport: IUnknown](imapisupportiunknown.md)方法进行通知时, MAPI 将使用隐藏窗口及其相应的窗口过程传递通知。</span><span class="sxs-lookup"><span data-stu-id="8be2c-105">When service providers use the [IMAPISupport : IUnknown](imapisupportiunknown.md) methods for notification, MAPI delivers notifications using a hidden window and its corresponding window procedure.</span></span> <span data-ttu-id="8be2c-106">对于每个接收通知的进程, MAPI 都会向隐藏窗口发布一条特殊消息。</span><span class="sxs-lookup"><span data-stu-id="8be2c-106">For each process to receive a notification, MAPI posts a special message to the hidden window.</span></span> <span data-ttu-id="8be2c-107">此消息使用 mapidefs.h 中定义的常量**szMAPINotificationMsg**进行命名。水平.</span><span class="sxs-lookup"><span data-stu-id="8be2c-107">This message is named with the constant **szMAPINotificationMsg** which is defined in MAPIDEFS.H.</span></span> 
  
<span data-ttu-id="8be2c-108">当隐藏窗口的窗口过程处理**szMAPINotificationMsg**消息时, 您会收到这些通知。</span><span class="sxs-lookup"><span data-stu-id="8be2c-108">You receive these notifications when the hidden window's window procedure processes the **szMAPINotificationMsg** message.</span></span> <span data-ttu-id="8be2c-109">若要确保传递通知, 需要等待并调度此**szMAPINotificationMsg**消息。</span><span class="sxs-lookup"><span data-stu-id="8be2c-109">To guarantee that notifications are delivered, it is necessary to wait for and dispatch this **szMAPINotificationMsg** message.</span></span> <span data-ttu-id="8be2c-110">实现此操作的逻辑只是很简单, 但 mapi 提供了名为[HrDispatchNotifications](hrdispatchnotifications.md)的 MAPI DLL 的入口点, 以便更简单地进行处理。</span><span class="sxs-lookup"><span data-stu-id="8be2c-110">Implementing the logic to achieve this can be done fairly simply, but MAPI provides an entry point into the MAPI DLL called [HrDispatchNotifications](hrdispatchnotifications.md) to make processing even simpler.</span></span> <span data-ttu-id="8be2c-111">按如下所示调用**HrDispatchNotifications**以在客户端中接收通知:</span><span class="sxs-lookup"><span data-stu-id="8be2c-111">Call **HrDispatchNotifications** as follows to receive notifications in your client:</span></span> 
  
```cpp
HRESULT hr = HrDispatchNotifications(0);
 
```


