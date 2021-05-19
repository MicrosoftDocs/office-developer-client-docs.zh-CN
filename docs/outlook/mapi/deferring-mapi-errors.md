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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427337"
---
# <a name="deferring-mapi-errors"></a>延迟 MAPI 错误

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
某些接口方法接受 MAPI_DEFERRED_ERRORS 标志作为输入参数。 设置此标志时，该方法无需立即返回值;它可以让呼叫者稍后知道呼叫结果。
  
延迟错误可帮助服务提供商实现复杂方法，从而加快处理速度。 延迟错误允许调用捆绑在服务提供商中，而不是处理许多请求并返回每个请求的值。 一次处理多个请求将减少网络流量，从而提高性能。 延迟错误在调用删除或复制属性时尤其有用，这非常耗时的操作。 
  
当客户端在未设置 MAPI_DEFERRED_ERRORS 标志的情况下进行调用时，服务提供商可以延迟错误而不考虑，也可以返回MAPI_E_TOO_COMPLEX。 大多数客户端应延迟错误作为一种首选策略来使调用失败。 
  
设置 MAPI_DEFERRED_ERRORS 标志将更改客户端的错误处理实现，因为返回的信息可以随时传递，而不是在计划的时间传递。 如果对错误执行任何操作太晚，或者原始请求的数据不再可用，可能会返回错误。 例如，如果客户端调用 **IMsgStore：：OpenEntry** 打开设置了 MAPI_DEFERRED_ERRORS 的已删除文件夹，则客户端将不知道该问题，除非进行 **IMAPIProp：：GetProps** 调用以检索文件夹的属性之一。 **GetProps** 随后将返回MAPI_E_NOT_FOUND。 
  
## <a name="see-also"></a>另请参阅



[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)

