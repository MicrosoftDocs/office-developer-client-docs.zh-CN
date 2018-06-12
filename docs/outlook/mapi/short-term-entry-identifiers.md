---
title: 短期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 948e007a-ad68-4abd-9720-204c6584beb5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f601971e61eb6430bef9d50b093642ee04b14044
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778780"
---
# <a name="short-term-entry-identifiers"></a>短期条目标识符

**适用于**： Outlook 
  
时的标识符必须快速构建和不需要时间或距离上次通过服务提供程序为对象分配的短期的项标识符。 只能通过当前工作站上当前会话的生存期保证短期的项标识符的唯一性。 通常，短期的项标识符是有效的仅直到松开它所表示的对象。 
  
短期条目标识符将分配到表中的行和对话框，其中所需提供数据快速浏览中的条目。 例如，消息存储提供程序将短期条目标识符分配给内容表中的邮件的行和收件人表中的收件人。 

客户端可以使用这些短期条目标识符打开由的表格行的对象。 但是，与可用于任何**OpenEntry**方法的长期条目标识符，应与容器的**OpenEntry**方法使用短期条目标识符。 
  
## <a name="implementing-short-term-entry-identifiers"></a>实现短期条目标识符

实现短期条目标识符的最常见方式如下：
  
- 发出的短期的项标识符的长期的标识符，保留所有标记取消设置相同。 
    
- 发出的短期条目标识符不同设置的所有标志的长期标识符。 
    
客户端可以确定第二种类型的短期条目标识符，通过检查其**abFlags**成员，如下所示： 
  
```cpp
abFlags[0] = 0xFF;
 
```

某些服务提供商清除创建短期条目标识符具有更高版本的有效性的一个或多个标志。 例如，以下**abFlags**成员表示可为多个日期或多个会话的短期条目标识符： 
  
```cpp
abFlags[0] = 0xFF & ~MAPI_NOW;
abFlags[0] = 0xFF & ~MAPI_THISSESSION;
 
```

客户端快速获取、 使用和放弃短期条目标识符。 大多数情况下，它们可以采用相同的方式长期条目标识符。 他们可以从表格、 传递给**OpenEntry**方法，并与**CompareEntryIDs**方法比较检索。 一个例外，也会永远不会返回从[IMAPIProp::GetProps](imapiprop-getprops.md)方法。 返回从**GetProps**属性始终是长期条目标识符。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 条目标识符](mapi-entry-identifiers.md)

