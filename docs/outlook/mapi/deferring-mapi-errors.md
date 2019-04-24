---
title: 延迟 MAPI 错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93ae6d54-41cd-433c-8124-eb07d71baa57
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0cf56a92190acfab1a941bc8d3ad0acc1f3e1f89
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338701"
---
# <a name="deferring-mapi-errors"></a>延迟 MAPI 错误

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些接口方法接受 MAPI_DEFERRED_ERRORS 标志作为输入参数。 设置此标志后, 方法不必立即返回值;它可以让呼叫者在以后某个时候知道该呼叫的结果。
  
延迟错误有助于服务提供程序实现复杂方法, 使处理速度更快。 延迟错误可以将呼叫捆绑到服务提供商中, 而不是处理多个请求并为每个请求返回一个值。 同时处理多个请求会减少网络流量, 从而提高性能。 在对删除或复制属性的调用中, 延迟错误尤其有用, 这可能是非常耗时的操作。 
  
当客户端在未设置只能以延迟方式处理的 MAPI_DEFERRED_ERRORS 标志的情况下进行呼叫时, 服务提供程序可以在不考虑或返回 MAPI_E_TOO_COMPLEX 的情况下延迟这些错误。 大多数客户端应将错误推迟为使呼叫失败的首选策略。 
  
设置 MAPI_DEFERRED_ERRORS 标志将更改客户端的错误处理实现, 因为可以在任何时间 (而不是在计划时间) 传递返回的信息。 如果要执行的操作太晚, 或者有关原始请求的数据已不再可用, 则可能会返回错误。 例如, 如果客户端调用**IMsgStore:: OpenEntry**以打开具有 MAPI_DEFERRED_ERRORS 集的已删除文件夹, 则客户端将不会知道该问题, 直到调用**IMAPIProp:: GetProps**调用以检索其中一个文件夹属性。 然后, **GetProps**将返回 MAPI_E_NOT_FOUND。 
  
## <a name="see-also"></a>另请参阅



[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)

