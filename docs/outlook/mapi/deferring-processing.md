---
title: 延迟处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a791b95f-56ad-493a-9ba5-fb4c7dd80e89
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2d3fbf8f7a725f121579066001715fb0bc6beba0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336930"
---
# <a name="deferring-processing"></a>延迟处理

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
尽可能将 MAPI_DEFERRED_ERRORS 标志传递给方法调用。 许多 MAPI 方法调用已经过优化, 可接受此标志, 从而导致提供程序推迟请求的任务, 直到可以同时执行多个任务, 或者您也可以等待结果不再执行。
  
例如, 如果将 MAPI_DEFERRED_ERRORS 传递给[IMsgStore:: OpenEntry](imsgstore-openentry.md)打开文件夹, 则可以延迟打开文件夹和可能的远程呼叫, 直到您执行另一个调用 (如调用文件夹的**GetHierarchyTable** ) 或**GetProps**方法。 **GetHierarchyTable**和**GetProps**都需要从服务提供商 (必须立即执行的任务) 返回数据。 
  
推迟处理的另一种方法就是不发出呼叫。 通过了解用户以及当用户可以感知资源或处理时间时, 您可以确定何时有必要进行呼叫。 在用户不会注意到或根本不会注意到的情况时, 可以通过调用来提高性能。
  
例如, 如果要从正在移动大量邮件的邮件存储中每秒接收多个通知, 请考虑这样一种情况。 将显示一个进度指示器, 以指示操作完成的百分比。 用户通常无法感知此操作在几秒钟后才会变慢。 因此, 如果要更新进度指示器, 则在启动移动操作至少四秒后才进行任何更改。 这将节省操作速度较快时的常见情况, 并在操作缓慢时及时通知用户。
  

