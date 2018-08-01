---
title: 取消通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: decd5d7d-1f47-47c2-b9c4-be0e652c99dd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8cd96dd22daeb98646a62672bd17f7de4d2f7dab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774625"
---
# <a name="canceling-a-notification"></a>取消通知

  
  
**适用于**： Outlook 
  
若要取消通知，客户端调用 advise 源**Unadvise**方法。 调用**Unadvise**很重要，因为它会导致要释放其引用您通知接收器的服务提供程序。 只要服务提供商维护通知接收器的引用，可以继续通知接收器接收[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)呼叫。 实际上，由于事件通知的异步性质，客户端可以通知即使成功**Unadvise**呼叫。 客户端必须能够在任何时间处理收到通知。 
  
服务提供程序实现不同，因为无法调用**Unadvise**取消通知的客户端无法假定任何有关提供程序将释放其引用其通知接收器。 某些服务提供商释放其引用时释放其 advise 源告知接收器。 某些服务提供程序不工作。 只要服务提供商维护通知接收器的引用，该通知接收器可以继续接收通知。 
  

