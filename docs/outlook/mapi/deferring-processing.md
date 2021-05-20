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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430929"
---
# <a name="deferring-processing"></a>延迟处理

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将MAPI_DEFERRED_ERRORS标志传递给方法调用。 许多 MAPI 方法调用已优化为接受此标志，导致提供程序要么将请求的任务推迟，直到可以同时执行多个任务，要么可以不再等待结果。
  
例如，如果将 MAPI_DEFERRED_ERRORS 传递到 [IMsgStore：：OpenEntry](imsgstore-openentry.md) 以打开文件夹，则打开文件夹和可能的远程调用可以延迟，直到您进行其他调用（如调用文件夹的 **GetHierarchyTable** 或 **GetProps** 方法）。 **GetHierarchyTable** 和 **GetProps** 都要求从服务提供商返回数据，这是一个必须立即执行的任务。 
  
延迟处理的另一种方式是直接不进行调用。 通过了解用户以及用户何时可以感知到资源消耗或处理时间，你可以确定何时进行调用有意义。 有机会在用户不会注意到或完全不发出呼叫时发出调用来提高性能。
  
例如，在每秒从移动大量邮件的邮件存储中接收多个通知时，请考虑这种情况。 将显示进度指示器以指示操作完成百分比。 在几秒钟过去之前，用户通常不会认为此操作很慢。 因此，如果要更新进度指示器，在启动移动操作至少四秒钟后不要进行更改。 这将在操作速度较快的常见情况下节省时间，并通知用户操作缓慢时及时通知用户。
  

