---
title: 取消通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: decd5d7d-1f47-47c2-b9c4-be0e652c99dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fb0972638fdd062c99040694222724566281024f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326402"
---
# <a name="canceling-a-notification"></a>取消通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要取消通知, 客户端需要调用建议源的**Unadvise**方法。 调用**Unadvise**非常重要, 因为它会导致服务提供程序释放其对您的通知接收器的引用。 只要服务提供商维护对通知接收器的引用, 通知接收器就可以继续接收[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md) calls。 事实上, 由于事件通知的异步特性, 即使在成功的**Unadvise**调用之后, 也可以通知客户端。 客户端必须能够随时处理通知回执。 
  
由于服务提供程序实现不同, 无法调用**Unadvise**以取消通知的客户端无法假定提供程序释放其通知接收器的引用时的任何信息。 某些服务提供商释放他们的参考, 以在发布其建议来源时通知接收器。 有些服务提供商不会。 只要服务提供商维护对通知接收器的引用, 该通知接收器即可继续接收通知。 
  

