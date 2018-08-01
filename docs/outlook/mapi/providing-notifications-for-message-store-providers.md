---
title: 提供邮件存储区提供程序的通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0e1cdba-ceb6-4a3f-8449-79d1a0ad1adf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3abb4ba67ff5f0cf2284fa9286b6968698877b84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778579"
---
# <a name="providing-notifications-for-message-store-providers"></a>提供邮件存储区提供程序的通知

  
  
**适用于**： Outlook 
  
可选通知时，它们是非常重要一部分正确消息存储提供程序。 客户端应用程序和 MAPI 后台处理程序都依赖从消息存储提供程序的通知，以提交传出消息或接收的传入消息时获得良好的性能。 客户端和 MAPI 后台处理程序可以正常而不会收到通知从消息存储提供程序，但它们不将能够向用户告知没有它们的消息存储中的更改。 通常，这意味着用户将无法看到他们的客户端下一步将打开的消息存储之前，已到达新邮件的接收文件夹。
  
通过调用[IMsgStore::Advise](imsgstore-advise.md)方法，客户端注册通知。 客户端传入[IMAPIAdviseSink: IUnknown](imapiadvisesinkiunknown.md)接口，一个位掩码，指示哪种类型的通知客户端是有兴趣接收，并指示邮件中的对象的**EntryID**存储**Advise**应用于请求。 相关事件发生时 （例如，当新邮件的接收文件夹中的消息存储到达） 对象中，消息存储提供程序或对象本身应调用[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的**所有IMAPIAdviseSink** ，已注册的事件类型的对象。 
  
即使您的消息存储提供程序从不通知中的邮件存储区中，更改其他 MAPI 组件仍应该实现**IMsgStore::Advise**返回 MAPI_E_NO_SUPPORT。 这将通知其他组件不希望从邮件的通知存储提供程序。 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

