---
title: 一次性地址
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9224c694-b26f-42c7-9404-ee2dd832cfbb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 504ae8dddbddb1c7049574b1bdcc575a10a62c8f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570091"
---
# <a name="one-off-addresses"></a>一次性地址

**适用于**： Outlook 2013 |Outlook 2016 
  
一次性地址用于向一次性收件人，没有任何会话的通讯簿容器中的相应条目的收件人发送邮件。 新条目添加到通讯簿或新收件人的传出邮件的收件人列表中时，客户端可以创建一次性地址。 可以是一次性地址添加到任何容器的可修改。
  
若要创建一个一次性地址，客户端，请使用特殊模板包含编辑控件以输入所有构成一次性地址的信息。 一次性地址，如地址的其他类型，使用预定义的格式。 一次性地址的格式，如下所示由 MAPI 进行定义：
  
`Display name[Address type:Email address]`
  
没有为此格式的六个组件和有关报价字符某些规则。 下表中介绍的组件。
  
|**组件**|**使用情况**|**说明**|
|:-----|:-----|:-----|
|显示名称  <br/> |可选  <br/> |如果不存在，则**IAddrBook::ResolveName**使用的电子邮件地址的可见部分用作显示名称。 可能包括空格。 有关详细信息，请参阅[IAddrBook::ResolveName](iaddrbook-resolvename.md)。  <br/> |
|[  <br/> |必需  <br/> |描绘的类型和地址信息的开头。  <br/> |
|]  <br/> |必需  <br/> |描绘的类型和地址信息的末尾。 如果此字符后面空格以外的任何内容，输入不被视为一个自定义收件人。  <br/> |
|地址类型  <br/> |必需  <br/> |地址; 类型映射到特定地址格式。 有关详细信息，请参阅[MAPI 地址类型](mapi-address-types.md)。  <br/> |
|:  <br/> |必需  <br/> |开来的电子邮件地址的地址类型。  <br/> |
|电子邮件地址  <br/> |必需  <br/> |收件人地址。 可能包括空格。  <br/> |
   
MAPI 使用报价字符的特定集允许地址包含左方括号 ([])，如逗号 （，） 的特殊字符和冒号 （:） 和一些 untypeable 字符，例如回车返回或线条源或任何其他十六进制等效。 报价字符是反斜杠 (\)。 因此，如果客户端或提供程序必须在地址插入反斜杠，它们必须低于它的报价字符 ("\\")。
  
客户端和服务提供商可以使用此报价技术中的任何 nonfixed，可键入字段。 例如，以下条目转换为用作显示名称，作为地址类型，MSPEER Bill 李和\\billll\in 作为电子邮件地址：
  
`Bill Lee[MSPEER:\\\\billl\in]`

要插入特殊 nontypeable 字符，客户端和服务提供商使用报价字符后跟 x 和两个十六进制数字表示等效其十六进制值。 例如，如果某个地址具有等同于回车符 nontypeable 字符返回，(\0d) 十六进制数，在客户端应输入为：
  
`Fax Recipient[fax:recipient\x0dbuilding\x0doffice\x0d555-1212\x0d]`

**IAddrBook::ResolveName**还会自动分析大多数 SMTP 地址，查找具有以下格式的地址： 
  
`XXX@YYY.ZZZ`

尽管不是所有可能的附加了 RFC822 格式进行处理，此自动分析足以满足大多数用户。 **ResolveName**包括此功能，以使用户可以直接在消息输入 SMTP 地址并转到 Internet 用户的消息。 XXX、 YYY 和 ZZZ 组件的地址可以是一个或多个字符。 At 符号 (@) 不能包含在地址 XXX、 YYY 或 ZZZ 组件和 YYY 组件也不能包含时间段。 由于以下字符是 SMTP 地址中的特殊字符，MAPI 自动转换为一次性地址包含这些字符的显示名称： 
  
- \>\>
    
- @
    
- \<\>
    
- .
    
每个一次性地址分配相应的一次性条目标识符。 若要使此工作分配，客户端调用**IAddrBook::CreateOneOff**和传输提供程序调用**IMAPISupport::CreateOneOff**。 有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。 处理传入消息时, 传输提供程序创建一次性条目标识符网关地址和传输类型的关联的通讯簿提供程序无法处理的地址。 传输提供程序检查邮件以确定它可以由传输类型相关联的通讯簿提供程序来处理中每个地址的类型。 如果它无法传输提供程序调用**IMAPISupport::CreateOneOff**一次性条目标识符与关联的地址。 
  
一次性条目标识符按以下顺序包括以下信息：
  
1. **MAPIUID**
    
2. 版本
    
3. Flags
    
4. 显示名称
    
5. 地址类型
    
6. 电子邮件地址
    
在调用**IAddrBook::CreateOneOff**和**IMAPISupport::CreateOneOff**，客户端和传输提供程序可以设置一个标志，指示由一次性地址的收件人可以处理带格式的文本或嵌入 OLE对象。 指示收件人可以处理带格式的文本和 OLE 对象，客户端和传输提供程序集_ulFlags_参数中的 MAPI_SEND_NO_RICH_INFO 标志。 然后，MAPI 将一次性收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。 当未设置此标志时，MAPI 设为 TRUE **PR_SEND_RICH_INFO** ，除非一次性地址被解释为 SMTP 地址。 在本例一个**PR_SEND_RICH_INFO**默认为 FALSE。 
  
## <a name="see-also"></a>另请参阅

- [IAddrBook::ResolveName](iaddrbook-resolvename.md)

