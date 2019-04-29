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
  
一个短期条目标识符由服务提供商分配给一个对象, 当该标识符必须能够快速构造且不需要在时间或距离上持续。 短期条目标识符的唯一性只能在当前工作站上的当前会话的生命周期内得到保证。 通常, 短期条目标识符仅在释放它所代表的对象时才有效。 
  
短期条目标识符分配给表中的行和对话框中的条目, 在这种情况下, 需要快速提供数据以供浏览。 例如, 邮件存储提供程序将短期条目标识符分配给内容表中的邮件行和收件人表中的收件人。 

客户端可以使用这些短期条目标识符打开表格行所代表的对象。 但是, 与可用于任何**OpenEntry**方法的长期条目标识符不同的是, 短期条目标识符应与容器的**OpenEntry**方法一起使用。 
  
## <a name="implementing-short-term-entry-identifiers"></a>实现短期条目标识符

实现短期输入标识符的最常见方法包括以下内容:
  
- 使短期条目标识符与长期标识符相同, 并将所有标志保留为未设置。 
    
- 将短期输入标识符与长期标识符进行不同, 设置所有标志。 
    
客户端可以通过检查其**abFlags**成员来标识第二种类型的短期条目标识符, 如下所示: 
  
```cpp
abFlags[0] = 0xFF;
 
```

一些服务提供商清除了一个或多个标志, 以创建具有更高有效性的短期条目标识符。 例如, 以下**abFlags**成员表示可用于多天或多个会话的短期条目标识符。 
  
```cpp
abFlags[0] = 0xFF & ~MAPI_NOW;
abFlags[0] = 0xFF & ~MAPI_THISSESSION;
 
```

客户端可快速获取、使用和丢弃短期条目标识符。 在大多数情况下, 可以按照与长期条目标识符相同的方式使用它们。 可以从表中检索它们, 并将其传递给**OpenEntry**方法, 并与**CompareEntryIDs**方法进行比较。 一个例外是从不从[IMAPIProp:: GetProps](imapiprop-getprops.md)方法返回。 从**GetProps**返回的属性始终为长期条目标识符。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 条目标识符](mapi-entry-identifiers.md)

