---
title: MAPI 条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 84c37696-da7a-42e0-b8c0-29658a6c9a48
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4c414b9f8a1d70fd5eea94da326674a749ccefe2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414961"
---
# <a name="mapi-entry-identifiers"></a>MAPI 条目标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
条目标识符是存储在 [ENTRYID](entryid.md) 结构中用于唯一标识和打开 MAPI 对象的二进制数据片段。 大多数 MAPI 对象都有条目标识符。 对象的条目标识符类似于文件的文件名。 但是，它们不可传输，并且不能用于除它们所基于的系统外的其他系统上。 
  
## <a name="entry-identifiers"></a>条目标识符

邮件存储提供程序向邮件存储、文件夹和邮件分配条目标识符;通讯簿提供商将它们分配给通讯簿容器、通讯组列表和邮件用户。 条目标识符还用于打开由表中的行表示的对象，如状态表中的状态对象。 对象在[PidTagEntryId PR_ENTRYID (PidTagEntryId](pidtagentryid-canonical-property.md)) 标识符。  
  
服务提供商创建、分配和检查条目标识符时，客户端应用程序仅将它们用作打开对象的工具。 对于客户端，条目标识符是二进制数据的不透明部分，与基础邮件系统无关。 
  
客户端调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索其 **PR_ENTRYID** 属性或表的 [IMAPITable：：QueryColumns](imapitable-querycolumns.md) 方法，以检索包含 **PR_ENTRYID 属性的列** 。 
  
条目标识符作为参数传递给 **OpenEntry** 和 **CompareEntryIDs** 方法。 多个 MAPI 对象实现 **OpenEntry** 和 **CompareEntryIDs** 方法。 使用 **OpenEntry，** 客户端可以打开对象。 使用 **CompareEntryIDs，** 客户端可以比较两个条目标识符，以确定它们是否引用同一个对象。 由于条目标识符不一定是二进制比较标识符，因此客户端必须通过 **CompareEntryIDs** 方法比较它们。 
  
客户端在调用服务提供商时应始终自然地传递一致的条目标识符，因为尽管服务提供商应处理任意对齐的条目标识符，但并非总是如此。 自然对齐的内存地址使计算机能够访问数据类型该地址上支持的任何地址，而不会生成对齐错误。 自然对齐因子通常与系统内存分配器使用的对齐因子相同，通常为 8 个字节。
  
条目标识符有两种类型：短期和长期。 短期条目标识符的构造速度更快，但仅在当前工作站上的当前会话期间才保证其唯一性。 长期条目标识符的有效期更长。 短期条目标识符主要用于表中的行和对话框中的条目，而长期条目标识符用于许多对象，如邮件、文件夹和通讯组列表。
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

