---
title: 为邮件存储提供程序提供通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0e1cdba-ceb6-4a3f-8449-79d1a0ad1adf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a28e6e6f008517a6b1c2c82dfa391b478963880f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419931"
---
# <a name="providing-notifications-for-message-store-providers"></a>为邮件存储提供程序提供通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
虽然通知是可选的，但通知是良好邮件存储提供程序的一个非常重要的部分。 客户端应用程序和 MAPI 后台处理程序依赖来自邮件存储提供程序的通知，在提交传出邮件或接收传入邮件时获得良好性能。 客户端和 MAPI 后台处理程序可以在不接收来自邮件存储提供程序的通知的情况下运行，但如果没有客户端和后台处理程序，它们将无法通知用户邮件存储中的更改。 通常，这意味着在客户端下次打开邮件存储的接收文件夹之前，用户将无法看到新邮件已到达。
  
客户端通过调用 [IMsgStore：：Advise 方法注册通知](imsgstore-advise.md) 。 客户端将传递 [IMAPIAdviseSink ： IUnknown](imapiadvisesinkiunknown.md)接口、一个指示客户端希望接收的通知类型的位掩码和一个指示建议请求所应用到的消息存储中的哪个对象的 **EntryID。**  当对象 (中发生相关事件时（例如，当新邮件到达邮件存储) 中的接收文件夹时，邮件存储提供程序或对象本身应为已注册该事件类型的所有 **IMAPIAdviseSink** 对象调用 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md)方法。 
  
即使邮件存储提供程序从未向其他 MAPI 组件通知邮件存储中的更改，它也应该实现 **IMsgStore：：Advise** 以返回MAPI_E_NO_SUPPORT。 这将通知其他组件不要收到来自邮件存储提供程序的通知。 
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

