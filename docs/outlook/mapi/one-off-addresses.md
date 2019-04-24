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
ms.openlocfilehash: e6bda55951d8df5c5da272750c631ec105b2ccf2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279634"
---
# <a name="one-off-addresses"></a>一次性地址

**适用于**：Outlook 2013 | Outlook 2016 
  
一次性地址用于向一次性收件人 (在任何会话的通讯簿容器中没有相应条目的收件人) 发送邮件。 客户端可以在向通讯簿添加新条目或向传出邮件的收件人列表中添加新条目时创建一次性地址。 可以将一次性地址添加到任何可修改的容器中。
  
若要创建一次性地址, 客户端应使用包含编辑控件的特殊模板, 以输入构成一次性地址的所有信息。 一次性地址, 如其他类型的地址, 使用预定义的格式。 一次性地址格式由 MAPI 定义, 如下所示:
  
`Display name[Address type:Email address]`
  
此格式有六个组件和一些关于引号字符的规则。 下表中介绍了这些组件。
  
|**组件**|**用法**|**说明**|
|:-----|:-----|:-----|
|可分辨名称 (DN)  <br/> |可选  <br/> |如果不存在, 则**IAddrBook:: ResolveName**使用电子邮件地址的可见部分作为显示名称。 可能包含空格。 有关详细信息, 请参阅[IAddrBook:: ResolveName](iaddrbook-resolvename.md)。  <br/> |
|[  <br/> |必需  <br/> |描述了类型和地址信息的开头。  <br/> |
|]  <br/> |必需  <br/> |描述了键入和地址信息的结尾。 如果除空格之外的任何内容都跟在此字符之后, 则不会将该条目视为自定义收件人。  <br/> |
|地址类型  <br/> |必需  <br/> |地址类型;映射到特定地址格式。 有关详细信息, 请参阅[MAPI 地址类型](mapi-address-types.md)。  <br/> |
|:  <br/> |必需  <br/> |将地址类型与电子邮件地址分隔开。  <br/> |
|电子邮件地址  <br/> |必需  <br/> |收件人的地址。 可能包含空格。  <br/> |
   
MAPI 使用特定的一组引用字符来允许地址包含特殊字符, 如逗号 (,)、左方括号 ([) 和冒号 (:)以及一些 untypeable 字符 (如回车符或换行符) 或任何其他十六进制等效项。 引号字符是反斜杠 (\)。 因此, 如果客户端或提供程序必须在地址中插入反斜杠, 则必须使用引号字符 ("\\") 将其 preceed。
  
客户端和服务提供商可以在任何 nonfixed (种) 字段中使用此报价技术。 例如, 以下条目转换为 "记帐名称"、"MSPEER" 作为 "地址类型" 和\\"billll\in" 作为电子邮件地址:
  
`Bill Lee[MSPEER:\\\\billl\in]`

若要插入特殊的 nontypeable 字符, 客户端和服务提供程序使用带引号的字符, 后跟 x 和2个十六进制数字来表示它们的十六进制等效项。 例如, 如果地址的 nontypeable 字符等于回车 (\0d), 则客户端会输入以下字符:
  
`Fax Recipient[fax:recipient\x0dbuilding\x0doffice\x0d555-1212\x0d]`

**IAddrBook:: ResolveName**还会自动分析大多数 SMTP 地址, 查找具有以下格式的地址: 
  
`XXX@YYY.ZZZ`

虽然并非所有可能的/rfc822 格式都得到处理, 但这种自动分析足以满足大多数用户的情况。 **ResolveName**包括此功能, 使用户能够直接在邮件中输入 SMTP 地址, 并让该邮件转到 Internet 用户。 XXX、YYY 和 ZZZ 组件的地址可以是一个或多个字符。 at 符号 (@) 不能包含在 XXX、yyy 或 ZZZ 地址组件中, YYY 组件也不能包含句点。 由于以下字符是 SMTP 地址中的特殊字符, 因此 MAPI 会自动将包含这些字符的显示名称转换为一次性地址: 
  
- \>\>
    
- @
    
- \<\>
    
- .
    
为每个一次性地址分配一个对应的一次性条目标识符。 若要进行此分配, 客户端可以调用**IAddrBook:: CreateOneOff**和 transport providers, 调用**IMAPISupport:: CreateOneOff**。 有关详细信息, 请参阅[IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md)和[IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md)。 在处理传入邮件时, 传输提供程序为网关地址和传输的关联通讯簿提供程序无法处理的地址创建一次性条目标识符。 传输提供程序检查邮件中每个地址的类型, 以确定是否可以通过与传输关联的通讯簿提供程序进行处理。 如果不能, 传输提供程序将调用**IMAPISupport:: CreateOneOff**以将地址与一次性条目标识符相关联。 
  
一次性条目标识符按以下顺序包含以下信息:
  
1. **MAPIUID**
    
2. Version
    
3. Flags
    
4. 可分辨名称 (DN)
    
5. 地址类型
    
6. 电子邮件地址
    
在对**IAddrBook:: CreateOneOff**和**IMAPISupport:: CreateOneOff**、客户端和传输提供程序的调用中, 可以设置一个标志, 该标志指示由一次性地址表示的收件人是否可以处理格式化文本或嵌入的 OLE对象. 若要指示收件人可以处理带格式的文本和 OLE 对象, 客户端和传输提供程序在_ulFlags_参数中设置 MAPI_SEND_NO_RICH_INFO 标志。 MAPI 然后将一次性收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性设置为 FALSE。 如果未设置此标志, 则 MAPI 会将**PR_SEND_RICH_INFO**设置为 TRUE, 除非将一次性地址解释为 SMTP 地址。 在这种情况下, **PR_SEND_RICH_INFO**默认为 FALSE。 
  
## <a name="see-also"></a>另请参阅

- [IAddrBook::ResolveName](iaddrbook-resolvename.md)

