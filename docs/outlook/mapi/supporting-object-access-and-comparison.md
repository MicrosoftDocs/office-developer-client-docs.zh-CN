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
  
服务提供程序可以使用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)和[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)方法打开并比较属于其提供程序的对象或其他提供程序: 
  
与[IMAPISession:: OpenEntry](imapisession-openentry.md) for 客户端一样, 提供程序可以使用其支持对象的**OpenEntry**方法访问任何对象, 只要他们知道对象的条目标识符即可。 与 session 方法不同, 支持方法要求您在_lpEntryID_参数中指定一个有效的条目标识符。 它不能为 NULL。 
  
若要说明传输提供程序如何使用**IMAPISupport:: OpenEntry**, 请考虑以下方案。 传输提供程序收到了格式为 rtf 格式的邮件, 并不知道目标收件人是否可以处理此格式。 在传递邮件之前, 传输提供程序需要执行以下操作:
  
1. 调用邮件的[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法以访问收件人表和收件人的条目标识符, 其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
2. 将条目标识符传递给**IMAPISupport:: OpenEntry**以打开收件人, 通常是邮件用户或通讯组列表。 应将_lpInterface_参数设置为 NULL, 因为提供程序无法提前知道收件人的对象类型。 支持对象的**OpenEntry**方法调用[IMAPISession:: OpenEntry](imapisession-openentry.md)以确定负责收件人的通讯簿提供程序。 然后, session 对象将调用相应的通讯簿提供程序的**OpenEntry**方法, 以打开收件人并将接口指针返回到传输提供程序。 
    
3. 调用收件人的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性。 如果将**PR_SEND_RICH_INFO**设置为 TRUE, 则收件人可以处理带格式的文本。 
    
如果您已从其他提供程序中打开了多个对象, 则可能需要了解两个条目标识符是否引用同一个对象。 例如, 您可能有一个短期条目标识符和一个长期条目标识符, 并且这些标识符可以标识同一个对象, 也可以不标识。 若要避免冗余处理, 请调用[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)方法来比较这些条目标识符。 由于条目标识符不能直接进行比较, 因此您必须使用此方法进行条目标识符比较。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

