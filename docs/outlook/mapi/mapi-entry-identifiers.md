---
title: MAPI 条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 84c37696-da7a-42e0-b8c0-29658a6c9a48
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b8212f4a055125858b77ee615a5d929a4a62bb82
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776222"
---
# <a name="mapi-entry-identifiers"></a>MAPI 条目标识符

  
  
**适用于**： Outlook 
  
条目标识符是存储在[ENTRYID](entryid.md)结构用于唯一标识，并打开 MAPI 对象的二进制数据的片段。 大多数 MAPI 对象具有条目标识符。 对象的项标识符是类似于文件的文件名。 但是，他们不可传送，并且不能使用它们在产生的系统之外的系统上。 
  
## <a name="entry-identifiers"></a>条目标识符

消息存储提供程序分配给消息存储库、 文件夹和消息; 条目标识符通讯簿提供程序将其分配给通讯簿容器、 通讯组列表和消息的用户。 条目标识符还用于打开由表，如状态表中的状态对象中的行对象。 对象在其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性中存储其条目标识符。 
  
服务提供商创建，分配，并检查条目标识符，而客户端应用程序将它们仅用作工具打开对象。 向客户端，条目标识符是二进制数据的不透明片段，并且没有执行与基础邮件系统。 
  
客户端调用对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_ENTRYID**属性或表的[IMAPITable::QueryColumns](imapitable-querycolumns.md)方法来检索包含**PR_ENTRYID**属性的列。 
  
条目标识符作为参数传递给**OpenEntry**和**CompareEntryIDs**方法。 几个 MAPI 对象实现的**OpenEntry**和**CompareEntryIDs**方法。 与**OpenEntry**，客户端可以打开一个对象。 **CompareEntryIDs**，使用客户端可以比较两个条目标识符来确定它们是否引用同一个对象。 因为条目标识符不一定是二进制比较，客户端必须对它们进行比较**CompareEntryIDs**方法。 
  
客户端应该与服务提供商，其呼叫总是传递自然地对齐的条目标识符，因为服务提供商应处理的任意位置对齐的项标识符，尽管这并不总是这种情况。 自然地对齐的内存地址允许访问它支持在该地址不生成对齐错误任何数据类型的计算机。 自然对齐系数通常由系统内存分配程序相同的对齐方式系数和通常是 8 字节。
  
条目标识符分为两种类型： 短期和长期。 短期条目标识符更快的构造，但其唯一性保证只能通过当前工作站上当前会话的生命周期。 长期条目标识符具有更多长时间的生命周期。 短期条目标识符主要用于表中的行和条目在对话框中，而长期条目标识符可用于多个对象，如信息、 文件夹和通讯组列表。
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

