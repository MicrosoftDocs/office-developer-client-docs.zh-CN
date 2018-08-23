---
title: 推迟 MAPI 错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93ae6d54-41cd-433c-8124-eb07d71baa57
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3d2a46be04f235ba55aa5f2feef222ea7372b211
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569860"
---
# <a name="deferring-mapi-errors"></a>推迟 MAPI 错误

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
一些接口方法接受 MAPI_DEFERRED_ERRORS 标志作为输入参数。 当此标志设置时，该方法不需要立即返回值;它可以让呼叫者了解在某些更高版本时调用的结果。
  
推迟错误帮助他们实现复杂方法中的服务提供商进行处理速度更快。 而不是处理大量请求和每个返回一个值，推迟错误允许无法捆绑的服务提供程序内的呼叫。 同时处理大量请求可以减少网络流量，从而提高性能。 推迟错误是要删除的呼叫或复制属性，可以是非常耗时的操作特别有用。 
  
服务提供商时没有设置 MAPI_DEFERRED_ERRORS 标志只能处理延迟的方式，客户端发出呼叫，可以将无论错误也推迟或返回 MAPI_E_TOO_COMPLEX。 大多数客户端应作为对失败的呼叫的首选策略推迟错误。 
  
设置 MAPI_DEFERRED_ERRORS 标志更改客户端的错误处理实现中，可以传递返回的信息，在任何时候，而不是计划的时间。 很可能会晚有关该产品，或有关原始请求的数据不再可用后执行任何操作时要返回的错误。 例如，如果客户端调用**IMsgStore::OpenEntry** MAPI_DEFERRED_ERRORS 设置打开已删除的文件夹，客户端将不知道问题的直到**IMAPIProp::GetProps**调用来检索文件夹的属性之一。 **GetProps**然后将返回 MAPI_E_NOT_FOUND。 
  
## <a name="see-also"></a>另请参阅



[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)

