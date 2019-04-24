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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297877"
---
# <a name="mapi-entry-identifiers"></a>MAPI 条目标识符

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
条目标识符是存储在[ENTRYID](entryid.md)结构中的一段二进制数据, 用于唯一标识和打开 MAPI 对象。 大多数 MAPI 对象都有条目标识符。 对象的条目标识符类似于文件的文件名。 但是, 它们不是传输, 不能在其起源的系统之外的系统上使用。 
  
## <a name="entry-identifiers"></a>条目标识符

邮件存储提供程序为邮件存储、文件夹和邮件分配条目标识符;通讯簿提供程序将其分配给通讯簿容器、通讯组列表和邮件用户。 条目标识符还用于打开由表中的行表示的对象, 例如状态表中的 status 对象。 对象在其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性中存储其条目标识符。 
  
虽然服务提供程序创建、分配和检查条目标识符, 但客户端应用程序仅将其用作打开对象的工具。 对于客户端, 条目标识符是不透明的二进制数据块, 与基础邮件系统无关。 
  
客户端调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_ENTRYID**属性或表的[IMAPITable:: QueryColumns](imapitable-querycolumns.md)方法以检索包含**PR_ENTRYID**属性的列。 
  
条目标识符作为参数传递给**OpenEntry**和**CompareEntryIDs**方法。 几个 MAPI 对象实现**OpenEntry**和**CompareEntryIDs**方法。 通过**OpenEntry**, 客户端可以打开对象。 通过**CompareEntryIDs**, 客户端可以对两个条目标识符进行比较, 以确定它们是否引用同一个对象。 由于条目标识符不一定是二进制可比较的, 因此客户端必须将其与**CompareEntryIDs**方法进行比较。 
  
客户端应始终在其对服务提供程序的调用中传递自然对齐的条目标识符, 因为尽管服务提供程序应处理任意对齐的条目标识符, 但这并不总是如此。 通过自然对齐的内存地址, 计算机可以访问它在该地址支持的任何数据类型, 而不会生成对齐错误。 自然对齐因子通常与系统内存分配器使用相同的校准因子, 并且通常为8个字节。
  
条目标识符分为两种类型: 短期和长期。 短期条目标识符的构建速度更快, 但仅在当前工作站上的当前会话的生命周期内保证它们的唯一性。 长期条目标识符的生命周期较长。 短期条目标识符主要用于表格中的行和对话框中的条目, 而长期条目标识符用于许多对象, 例如邮件、文件夹和通讯组列表。
  
## <a name="see-also"></a>另请参阅



[MAPI 应用程序开发](mapi-application-development.md)

