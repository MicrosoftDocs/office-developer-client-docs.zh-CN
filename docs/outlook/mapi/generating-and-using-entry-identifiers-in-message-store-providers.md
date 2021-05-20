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
  
在邮件存储中新建文件夹或邮件时，邮件存储提供程序必须向该对象分配条目标识符，以便客户端应用程序可以引用该对象。 邮件存储提供程序可以重用已删除对象的已失效长期条目标识符，也可以创建新的标识符。 对邮件存储提供程序没有一种或另一种要求;但是，如果可行，邮件存储提供程序应始终为新对象生成新的长期条目标识符，而不是重新使用旧对象。 在删除其引用的对象时，可以重用短期条目标识符。
  
此删除的原因是客户端可以缓存条目标识符，有时可以缓存很长时间。 如果发生这种情况并且邮件存储提供程序确实重复使用条目标识符，则当客户端打开条目标识符时，条目标识符可以引用与客户端首次获取条目标识符时不同的对象。 如果邮件存储提供程序不重用条目标识符（或者至少使用不会长时间重复的条目标识符生成方案）则不会发生此问题。
  
同样，当文件夹和邮件在邮件存储中移动时，邮件存储提供程序应尝试保留这些文件夹和邮件的条目标识符。 如果邮件存储提供程序可以这样做，当对象移动到存储区中的不同位置时，对存储中的对象的引用不会变为无效。
  
## <a name="see-also"></a>另请参阅

- [邮件存储功能](message-store-features.md)

