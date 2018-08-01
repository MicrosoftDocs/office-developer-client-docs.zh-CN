---
title: 强制执行通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9c7d6605-73ee-468c-981b-e0853106c9ba
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 40fc763071f7113e222c6987dfd70fb7d89bab4b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774960"
---
# <a name="forcing-a-notification"></a><span data-ttu-id="2ca1d-103">强制执行通知</span><span class="sxs-lookup"><span data-stu-id="2ca1d-103">Forcing a Notification</span></span>

  
  
<span data-ttu-id="2ca1d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2ca1d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2ca1d-105">当服务提供商使用[IMAPISupport: IUnknown](imapisupportiunknown.md)的通知，MAPI 方法提供了使用隐藏的窗口和其对应的窗口过程的通知。</span><span class="sxs-lookup"><span data-stu-id="2ca1d-105">When service providers use the [IMAPISupport : IUnknown](imapisupportiunknown.md) methods for notification, MAPI delivers notifications using a hidden window and its corresponding window procedure.</span></span> <span data-ttu-id="2ca1d-106">为每个过程以接收通知，MAPI 发送给隐藏窗口的特殊的消息。</span><span class="sxs-lookup"><span data-stu-id="2ca1d-106">For each process to receive a notification, MAPI posts a special message to the hidden window.</span></span> <span data-ttu-id="2ca1d-107">使用常量**szMAPINotificationMsg**中 MAPIDEFS 定义命名此消息。H。</span><span class="sxs-lookup"><span data-stu-id="2ca1d-107">This message is named with the constant **szMAPINotificationMsg** which is defined in MAPIDEFS.H.</span></span> 
  
<span data-ttu-id="2ca1d-108">当隐藏的窗口的窗口过程处理**szMAPINotificationMsg**邮件，您会收到这些通知。</span><span class="sxs-lookup"><span data-stu-id="2ca1d-108">You receive these notifications when the hidden window's window procedure processes the **szMAPINotificationMsg** message.</span></span> <span data-ttu-id="2ca1d-109">若要确保将发送通知，它和所需等待调度此**szMAPINotificationMsg**消息。</span><span class="sxs-lookup"><span data-stu-id="2ca1d-109">To guarantee that notifications are delivered, it is necessary to wait for and dispatch this **szMAPINotificationMsg** message.</span></span> <span data-ttu-id="2ca1d-110">可以相当简单，完成实现逻辑以完成此任务，但 MAPI 提供了 MAPI DLL 入口点调用[HrDispatchNotifications](hrdispatchnotifications.md)进行处理甚至更简单。</span><span class="sxs-lookup"><span data-stu-id="2ca1d-110">Implementing the logic to achieve this can be done fairly simply, but MAPI provides an entry point into the MAPI DLL called [HrDispatchNotifications](hrdispatchnotifications.md) to make processing even simpler.</span></span> <span data-ttu-id="2ca1d-111">呼叫**HrDispatchNotifications** ，如下所示，以在您的客户端接收通知：</span><span class="sxs-lookup"><span data-stu-id="2ca1d-111">Call **HrDispatchNotifications** as follows to receive notifications in your client:</span></span> 
  
```cpp
HRESULT hr = HrDispatchNotifications(0);
 
```


