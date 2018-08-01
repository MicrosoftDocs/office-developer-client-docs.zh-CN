---
title: 延迟处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a791b95f-56ad-493a-9ba5-fb4c7dd80e89
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8f26fc6a51c3abdb4d4d009183fa8263ce97b261
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774750"
---
# <a name="deferring-processing"></a>延迟处理

  
  
**适用于**： Outlook 
  
传递给方法调用 MAPI_DEFERRED_ERRORS 标志尽可能。 已优化的 MAPI 方法调用许多接受此标志，导致的提供程序，也可以同时执行多个任务或可以等待不再结果之前延迟请求的任务。
  
例如，如果 MAPI_DEFERRED_ERRORS 传递给[IMsgStore::OpenEntry](imsgstore-openentry.md)打开一个文件夹，打开的文件夹和可能的远程呼叫可以被延迟，直到您进行另一个呼叫，如调用该文件夹的**通讯**或**GetProps**方法。 **通讯**和**GetProps**需要从服务提供商，必须立即执行的任务的数据返回。 
  
延迟处理另一种方法是只需不发起呼叫。 通过注意的用户和用户可以感知处理时间或资源耗尽，您可以确定时有意义发起呼叫。 没有机会来提高性能，通过调用可以一次用户将不注意到或根本不进行。
  
当您从移动大量的消息的消息存储收到每秒的多个通知，例如，假设这种情况。 显示进度指示器以指示该操作完成百分比。 用户通常将不会察觉此操作会较慢，直到过去几秒钟。 因此，如果您正在更新进度指示器，不要任何更改之前，至少 4 秒后移动操作的初始。 将 fast 操作时的常见情况节省时间并操作太慢时正在及时通知用户。
  

