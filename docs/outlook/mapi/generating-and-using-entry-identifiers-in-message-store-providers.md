---
title: 生成和使用邮件存储提供程序中的条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0c43546a-4788-4852-bc89-d6baa4f33c94
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 005742eaaba81600be249d52e5d8098e9f286f17
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437677"
---
# <a name="generating-and-using-entry-identifiers-in-message-store-providers"></a>生成和使用邮件存储提供程序中的条目标识符

**适用于**：Outlook 2013 | Outlook 2016 
  
在邮件存储区中创建新文件夹或邮件时, 邮件存储提供程序必须为该对象分配条目标识符, 以便客户端应用程序可以引用它。 邮件存储提供程序可以重用已删除对象的失效期限项标识符, 也可以创建新的标识符。 邮件存储提供程序不需要一种方法, 也不需要另一种方法;但是, 如果可行, 邮件存储提供程序应始终为新对象生成新的长期条目标识符, 而不是重新使用旧的条目标识符。 在删除的对象所引用的对象被删除时, 可以使用短期条目标识符。
  
此删除的原因是, 客户端可以缓存条目标识符 (有时在很长一段时间内)。 如果发生这种情况, 且邮件存储提供程序确实在重新使用条目标识符, 则当客户端打开条目标识符时, 条目标识符可能会引用其他对象, 而不是首次获取条目标识符时。 如果邮件存储区提供程序不重复使用条目标识符, 或者至少使用的条目标识符生成方案在很长时间里不重复, 则不会发生此问题。
  
同样, 邮件存储提供程序应尝试在邮件存储区中移动文件夹和邮件时保留条目标识符。 如果邮件存储区提供程序可以执行此操作, 则在将对象移动到存储区中的其他位置时, 对 store 中的对象的引用将不会变为无效。
  
## <a name="see-also"></a>另请参阅

- [邮件存储区功能](message-store-features.md)

