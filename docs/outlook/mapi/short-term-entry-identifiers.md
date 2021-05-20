---
title: 短期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 948e007a-ad68-4abd-9720-204c6584beb5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1b361e025b631418eb63c5c74da264beadec2974
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439560"
---
# <a name="short-term-entry-identifiers"></a>短期条目标识符

**适用于**：Outlook 2013 | Outlook 2016 
  
当必须快速构造标识符并且不需要在一段时间或一段距离内持续时，服务提供商将短期条目标识符分配给对象。 短期条目标识符的唯一性仅在当前工作站上的当前会话的生命周期内得到保证。 通常，短期条目标识符仅在它所代表的对象释放之前有效。 
  
短期条目标识符分配给表中的行和对话框中的条目，其中需要快速提供数据以便浏览。 例如，邮件存储提供程序将短期条目标识符分配给内容表中的邮件行和收件人表中的收件人。 

客户端可以使用这些短期条目标识符打开表行表示的对象。 但是，与可用于任何 **OpenEntry** 方法的长期条目标识符不同，短期条目标识符应该与容器的 **OpenEntry** 方法一同使用。 
  
## <a name="implementing-short-term-entry-identifiers"></a>实现短期条目标识符

实现短期条目标识符的最常见方法包括：
  
- 使短期条目标识符与长期标识符相同，不设置所有标志。 
    
- 使短期条目标识符不同于长期标识符，并设置所有标志。 
    
客户端可以通过检查其 **abFlags** 成员来标识第二种类型的短期条目标识符，如下所示： 
  
```cpp
abFlags[0] = 0xFF;
 
```

某些服务提供商清除一个或多个标志以创建有效性更高的短期条目标识符。 例如，以下 **abFlags** 成员表示可用于多天或多个会话的短期条目标识符： 
  
```cpp
abFlags[0] = 0xFF & ~MAPI_NOW;
abFlags[0] = 0xFF & ~MAPI_THISSESSION;
 
```

客户端可以快速获取、使用和放弃短期条目标识符。 大多数情况下，可以使用与长期条目标识符相同的方式使用它们。 可以从表中检索它们，将其传递给 **OpenEntry** 方法，并与 **CompareEntryIDs** 方法进行比较。 一个例外是，从不会从 [IMAPIProp：：GetProps 方法返回](imapiprop-getprops.md) 它们。 从 **GetProps** 返回的属性始终是长期条目标识符。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 条目标识符](mapi-entry-identifiers.md)

