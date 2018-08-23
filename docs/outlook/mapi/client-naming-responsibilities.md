---
title: 客户端命名责任
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dbb6ba5f-18c8-426f-9f50-ce6f2fd1dc5b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f47193bf8866622fa2e6d1f849d0568471c5461c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580780"
---
# <a name="client-naming-responsibilities"></a>客户端命名责任

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端必须遵循需要翻译的网关及其属性的命名约定。 要转换的所有属性应将都创建为命名属性指定用于保存可映射属性的五个属性集之一：
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
PS_ROUTING_SEARCH_KEY
  
解决与同一用户相关的属性必须提供相同的名称。 网关都依赖以下命名约定，使他们能够与其正确的地址类型相匹配的地址。 用于地址解析，必须准确地址和地址类型之间的映射。
  
与**MAPINAMEID**数据结构，用于指定属性名称可以是一个 Unicode 字符串或 32 位整数表示 MAPI 命名属性。 有关详细信息，请参阅[MAPINAMEID](mapinameid.md)。 整数命名被建议组的地址中，因为它是区分的可映射属性集的简单方法，它可以轻松地作为用户的索引。 使用整数的替代方法是作为所有五个用户的可映射属性的名称分配一个字符串。 如果只有一个用户需要映射，将字符串分配是可以接受。 但是，如果有多个用户，则最好使用整数命名。 名称，它是基于数字或字符串的是否应存储中的邮件类特定属性或属于由客户端应用程序定义的属性集属性中。 
  
> [!NOTE]
> 避免转换为字符串，例如"route_recipient_1"和"route_recipient_2。"整数名称 这项成果是不必要的。 
  
为了理解以下命名约定的工作方式，请考虑的路由应用程序的每个四人团队成员发送一条消息。 当一个成员收到邮件时，他/她必须对其做出响应之前将其发送到的下一个成员的编译响应以及。 原始邮件包含收件人列表包含一个条目： 团队的第一个成员。 邮件中的嵌入供其他三个团队成员的网关可映射的属性。 每个成员具有驻留在网关可映射的属性集，分配的唯一数字的名称中的五个核心用户属性。 
  
下表说明了为每个网关可映射的剩余邮件路由到其完成它的第一个工作组成员时的工作组成员的三个存储的属性集的设置。
  
|**Property Set**|**第二个团队<br/>成员**|**第 3 个团队<br/>成员**|**第四个团队<br/>成员**|
|:-----|:-----|:-----|:-----|
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |地址 = 0  <br/> |地址 = 1  <br/> |地址 = 2  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |地址类型 = 0  <br/> |地址类型 = 1  <br/> |地址类型 = 2  <br/> |
|PS_ROUTING_DISPLAY_NAME  <br/> |显示名称 = 0  <br/> |显示名称 = 1  <br/> |显示名称 = 2  <br/> |
|PS_ROUTING_ENTRYID  <br/> |项标识符 = 0  <br/> |项标识符 = 1  <br/> |项标识符 = 2  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |搜索关键字 = 0  <br/> |搜索关键字 = 1  <br/> |搜索关键字 = 2  <br/> |
   
使用作为引用其他邮件属性可映射搜索键的客户端必须能够识别除非它们放在这些可映射的属性集之一，将不转换其他邮件属性。 当包含未映射引用映射的搜索关键字的消息发送到另一个消息域中的目标时，引用是无效。 若要启用这些其他属性，以便与搜索关键字保持同步，您可以将其分配 PS_ROUTING_SEARCH_KEY 设置的属性中不会干扰分配给任何核心可映射属性的名称的字符串名称。 例如，假设客户端需要传输包含搜索键长路由列表中的最后一个人的属性。 客户端可以在名为"last_search_key。"PS_ROUTING_SEARCH_KEY 属性集中创建命名的属性 由于该记录存储在可映射的属性集，以及其他网关可映射属性转换"last_search_key"属性。
  

