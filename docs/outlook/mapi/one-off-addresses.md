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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409109"
---
# <a name="one-off-addresses"></a>一次性地址

**适用于**：Outlook 2013 | Outlook 2016 
  
一对一地址用于向一次收件人（该收件人在任何会话的通讯簿容器中没有对应条目的收件人）发送邮件。 客户端在将新条目添加到通讯簿或将新收件人添加到传出邮件的收件人列表时，可以创建一次地址。 一次使用地址可以添加到任何可修改的容器中。
  
若要创建一次地址，客户端使用包含编辑控件的特殊模板来输入所有信息，这些信息将形成一次地址。 一次使用地址（如其他类型的地址）使用预定义格式。 一次地址格式由 MAPI 定义，如下所示：
  
`Display name[Address type:Email address]`
  
此格式包含六个要素和一些有关引用字符的规则。 下表介绍了这些组件。
  
|**组件**|**用法**|**说明**|
|:-----|:-----|:-----|
|显示名称  <br/> |可选  <br/> |如果不存在 **，IAddrBook：：ResolveName** 使用电子邮件地址的可见部分作为显示名称。 可能包括空白。 有关详细信息，请参阅 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)。  <br/> |
|[  <br/> |必需  <br/> |描述类型和地址信息的开始。  <br/> |
|]  <br/> |必需  <br/> |描述类型和地址信息的结尾。 如果此字符后跟空格外的其他任何内容，则不将条目视为自定义收件人。  <br/> |
|地址类型  <br/> |必需  <br/> |地址类型;映射到特定地址格式。 有关详细信息，请参阅 [MAPI 地址类型](mapi-address-types.md)。  <br/> |
|:  <br/> |必需  <br/> |将地址类型与电子邮件地址分开。  <br/> |
|电子邮件地址  <br/> |必需  <br/> |收件人的地址。 可能包括空白。  <br/> |
   
MAPI 使用特定的引文字符集允许地址包含特殊字符，如逗号 (，) 、左方括号 ([) 和冒号 (：) 以及一些不可键入的字符，如回车符或换行符或其他任何十六进制等效字符。 该引文字符是反杠 (\) 。 因此，如果客户端或提供商必须在地址中插入反杠，则必须在地址前加一个 \\ ("") 。
  
客户端和服务提供商可以在任何非fixed的可键入字段中使用此引文技术。 例如，以下条目转换为 Bill Lee 作为显示名称，将 MSPEER 转换为地址类型， \\ 将 billll\in 转换为电子邮件地址：
  
`Bill Lee[MSPEER:\\\\billl\in]`

为了插入特殊不可键入的字符，客户端和服务提供商使用后跟 x 和两个十六进制数字的商数来表示它们的十六进制等效字符。 例如，如果地址具有一个等号为回车的不可键入字符， (\0d) 十六进制，则客户端会按如下方式输入：
  
`Fax Recipient[fax:recipient\x0dbuilding\x0doffice\x0d555-1212\x0d]`

**IAddrBook：：ResolveName** 还自动分析大多数 SMTP 地址，查找具有以下格式的地址： 
  
`XXX@YYY.ZZZ`

虽然并非所有可能的 RFC822 格式都得到处理，但此自动分析足以满足大多数用户的需求。 **ResolveName** 包含此功能，使用户可以直接在邮件中输入 SMTP 地址，并且使该邮件转到 Internet 用户。 地址的 XXX、YYY 和 ZZZ 组件可以是一个或多个字符。 AT 符号 (@) 不能包含在 XXX、YYY 或 ZZZ 地址组件中，并且 YYY 组件也不能包含期间。 由于以下字符是 SMTP 地址中的特殊字符，MAPI 会自动显示名称包含这些字符的字符串转换为一次地址： 
  
- \>\>
    
- @
    
- \<\>
    
- .
    
每个一次地址都分配有一个对应的一次输入标识符。 为了进行此分配，客户端调用 **IAddrBook：：CreateOneOff，** 传输提供程序 **调用 IMAPISupport：：CreateOneOff**。 有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md) 和 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)。 处理传入邮件时，传输提供程序会为网关地址和传输的关联通讯簿提供程序无法处理的地址创建一次条目标识符。 传输提供程序检查邮件中每个地址的类型，以确定该地址是否可以通过与传输关联的通讯簿提供程序进行处理。 如果无法，传输提供程序将调用 **IMAPISupport：：CreateOneOff** 以将地址与一次输入标识符关联。 
  
一次输入标识符按以下顺序包含以下信息：
  
1. **MAPIUID**
    
2. 版本
    
3. Flags
    
4. 显示名称
    
5. 地址类型
    
6. 电子邮件地址
    
在调用 **IAddrBook：：CreateOneOff** 和 **IMAPISupport：：CreateOneOff** 时，客户端和传输提供程序可以设置一个标志，指示一次使用地址表示的收件人是否可以处理格式化的文本或嵌入的 OLE 对象。 为了指示收件人可以处理格式化的文本和 OLE 对象，客户端和传输提供程序在  _ulFlags_ MAPI_SEND_NO_RICH_INFO设置 MAPI_SEND_NO_RICH_INFO 标记。 然后，MAPI 将[PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md) PR_SEND_RICH_INFO (一次收件人) 属性为 FALSE。  未设置此标志时，MAPI PR_SEND_RICH_INFO设置为 TRUE，除非一次使用的地址被解释为 SMTP 地址。 在这一 **种情况下，PR_SEND_RICH_INFO** 默认值为 FALSE。 
  
## <a name="see-also"></a>另请参阅

- [IAddrBook::ResolveName](iaddrbook-resolvename.md)

