---
title: 支持对象访问和比较
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aac7c6c5-6896-4824-ba36-81bb292777a9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2b62f92325fcebf8cd3f0c86d28d98e7ff511ee2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429031"
---
# <a name="supporting-object-access-and-comparison"></a>支持对象访问和比较

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
服务提供商可以使用 [IMAPISupport：：OpenEntry](imapisupport-openentry.md) 和 [IMAPISupport：：CompareEntryIDs](imapisupport-compareentryids.md) 方法打开并比较属于其提供程序或其他提供程序的对象： 
  
与 [适用于客户端的 IMAPISession：：OpenEntry](imapisession-openentry.md) 一样，提供程序可以使用其支持对象的 **OpenEntry** 方法访问任何对象，只要他们知道对象的条目标识符。 与会话方法不同，支持方法要求在  _lpEntryID_ 参数中指定有效的条目标识符。 它不能为 NULL。 
  
为了说明传输提供程序如何使用 **IMAPISupport：：OpenEntry，** 请考虑以下方案。 传输提供程序已收到格式为富文本格式的邮件，并且不知道目标收件人是否可以处理此格式。 在传递邮件之前，传输提供程序需要执行以下操作：
  
1. 调用邮件的[IMessage：：GetRecipientTable](imessage-getrecipienttable.md)方法以访问收件人表和收件人的条目标识符、PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 
    
2. 将条目标识符传递到 **IMAPISupport：：OpenEntry** 以打开收件人，通常是邮件用户或通讯组列表。 _lpInterface_ 参数应设置为 NULL，因为提供程序无法提前知道收件人对象类型的名称。 支持对象的 **OpenEntry** 方法调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 来确定负责收件人的通讯簿提供程序。 然后，会话对象调用相应的通讯簿提供程序的 **OpenEntry** 方法以打开收件人，并返回指向传输提供程序的接口指针。 
    
3. 调用收件人的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来 **检索其** PR_SEND_RICH_INFO ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性。 如果 **PR_SEND_RICH_INFO** 设置为 TRUE，则收件人可以处理格式化的文本。 
    
如果您打开了其他提供程序中的多个对象，您可能需要了解两个条目标识符是否引用同一个对象。 例如，你可能有一个短期条目标识符和一个长期条目标识符，这些标识符可能标识同一个对象，也可以不标识同一个对象。 为了避免冗余处理，请调用 [IMAPISupport：：CompareEntryIDs](imapisupport-compareentryids.md) 方法来比较这些条目标识符。 必须使用此方法进行条目标识符比较，因为不能直接比较条目标识符。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

