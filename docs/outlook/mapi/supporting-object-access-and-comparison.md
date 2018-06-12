---
title: 支持对象访问和比较
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aac7c6c5-6896-4824-ba36-81bb292777a9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2152cfbb91f2e343ebcee3f5b717a29805df1d25
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778938"
---
# <a name="supporting-object-access-and-comparison"></a>支持对象访问和比较

  
  
**适用于**： Outlook 
  
服务提供商可以使用[IMAPISupport::OpenEntry](imapisupport-openentry.md)和[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)方法打开和比较属于其提供程序或其他提供程序的对象： 
  
客户端[IMAPISession::OpenEntry](imapisession-openentry.md) ，如提供程序可以使用其支持对象的**OpenEntry**方法来访问任何对象，如长他们知道对象的项标识符。 会话与方法不同，支持方法需要_lpEntryID_参数中指定一个有效项标识符。 它不能为 NULL。 
  
为了说明如何传输提供程序可能使用**IMAPISupport::OpenEntry**，请考虑下面的方案。 传输提供程序已收到邮件格式的富文本格式，并不知道目标接收人是否可以处理此格式。 邮件传递之前, 传输提供程序需要执行以下操作：
  
1. 调用消息的[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法，以访问收件人表和收件人的项标识符，其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
2. 向**IMAPISupport::OpenEntry**打开收件人，通常任一消息的用户或通讯组列表传递的项标识符。 _LpInterface_参数应设置为 NULL，因为提供程序无法知道提早制定的收件人对象类型。 支持对象的**OpenEntry**方法调用[IMAPISession::OpenEntry](imapisession-openentry.md)确定负责收件人的地址簿提供程序。 会话对象将调用相应的通讯簿提供程序的**OpenEntry**方法以打开收件人，并返回到传输提供程序的接口指针。 
    
3. 调用收件人的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性。 如果**PR_SEND_RICH_INFO**设置为 TRUE，则收件人可处理带格式的文本。 
    
如果您已经从其他提供程序打开多个对象，您可能需要以找出两个条目标识符是否引用同一个对象。 例如，您可能遇到的短期条目标识符和长期的项标识符和这些标识符可能也可能未识别相同的对象。 若要避免冗余处理，调用[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)方法以比较这些条目标识符。 您必须使用此方法的项标识符比较，因为条目标识符不能直接进行比较。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

