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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328467"
---
# <a name="providing-notifications-for-message-store-providers"></a>为邮件存储提供程序提供通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
虽然通知是可选的, 但它们是良好邮件存储提供程序的一个非常重要的部分。 在提交传出邮件或接收传入邮件时, 客户端应用程序和 MAPI 后台处理程序依赖来自邮件存储提供程序的通知, 以获得更好的性能。 客户端和 MAPI 后台处理程序可以正常运行, 而无需接收来自邮件存储提供程序的通知, 但他们无法通知用户邮件存储区中的更改。 通常情况下, 这意味着用户将无法看到新邮件已到达, 直到其客户端下一步打开邮件存储的接收文件夹。
  
客户端通过调用[IMsgStore:: Advise](imsgstore-advise.md)方法注册通知。 客户端在[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口中传递, 指示客户端所要接收的通知类型的位掩码, 以及指示邮件存储中的哪个对象的**条目**。**建议**请求适用于。 当对象中发生相关事件时 (例如, 当新邮件到达邮件存储区中的接收文件夹时), 邮件存储提供程序或对象本身应调用[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法的所有**** 已为该事件类型注册的 IMAPIAdviseSink 对象。 
  
即使您的邮件存储提供程序永远不会向其他 MAPI 组件通知邮件存储区中发生的更改, 它仍应实现**IMsgStore:: 建议**返回 MAPI_E_NO_SUPPORT。 这会通知其他组件不会收到来自邮件存储提供程序的通知。 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

