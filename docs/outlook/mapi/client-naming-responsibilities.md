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
ms.openlocfilehash: 808c7abf3d29872a8c5095fdc6dc39b2107a8993
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424950"
---
# <a name="client-naming-responsibilities"></a>客户端命名责任

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端必须遵循其属性的命名约定, 需要由网关进行转换。 要转换的所有属性都应作为命名属性在指定用于保留可映射属性的五个属性集之一中创建:
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
PS_ROUTING_SEARCH_KEY
  
与同一用户相关的寻址属性必须具有相同的名称。 网关依赖于此命名约定, 这将使其能够匹配地址类型正确的地址。 对于地址分析, 地址和地址类型之间的映射必须准确。
  
名为的 MAPI 属性用**MAPINAMEID**数据结构表示, 该数据结构指定属性名称可以是 Unicode 字符串, 也可以是32位整数。 有关详细信息, 请参阅[MAPINAMEID](mapinameid.md)。 对于地址组, 建议使用整数命名, 因为它是区分可映射属性集的简单方法, 并且可以轻松地充当用户的索引。 使用整数的替代方法是将一个字符串指定为用户的可映射属性中的所有五个的名称。 如果只有一个用户需要映射, 则分配一个字符串是可接受的。 但是, 如果有多个用户, 最好使用整数命名。 名称 (无论是数字还是基于字符串) 都应存储在特定于邮件类别的属性中, 或者存储在由客户端应用程序定义的属性集的属性中。 
  
> [!NOTE]
> 避免将整数名称转换为字符串, 例如 "route_recipient_1" 和 "route_recipient_2"。 这一工作是不必要的。 
  
若要说明此命名约定的工作原理, 请考虑将邮件发送给四个人团队的每个成员的路由应用程序。 当一个成员收到邮件时, 他或她必须先对其做出响应, 然后才能将其与编译的下一个成员的响应一起发送。 原始邮件包含一个收件人列表, 其中包含一个条目: 团队的第一个成员。 嵌入在邮件中的是其他三个工作组成员的网关可映射属性。 每个成员都有五个核心用户属性, 这些属性位于网关可映射属性集内, 它们被分配了一个唯一的名称。 
  
下表说明了在第一个团队成员完成邮件时, 为该邮件路由到的三个剩余团队成员的每个组的网关可映射属性的设置。
  
|**Property Set**|**第二<br/>个工作组成员**|**第三<br/>个团队成员**|**第四<br/>个工作组成员**|
|:-----|:-----|:-----|:-----|
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |Address = 0  <br/> |Address = 1  <br/> |Address = 2  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |地址类型 = 0  <br/> |地址类型 = 1  <br/> |地址类型 = 2  <br/> |
|PS_ROUTING_DISPLAY_NAME  <br/> |显示名称 = 0  <br/> |显示名称 = 1  <br/> |显示名称 = 2  <br/> |
|PS_ROUTING_ENTRYID  <br/> |条目标识符 = 0  <br/> |条目标识符 = 1  <br/> |条目标识符 = 2  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |搜索关键字 = 0  <br/> |搜索关键字 = 1  <br/> |搜索关键字 = 2  <br/> |
   
使用可映射的搜索关键字作为对其他邮件属性的引用的客户端必须认识到, 除非将其他邮件属性放置在这些可映射的属性集之一中, 否则这些属性将不会被转换。 当向另一个邮件域中的目标发送带有未映射的搜索关键字引用的邮件时, 引用将无效。 若要使这些其他属性保持与搜索关键字同步, 可以在 PS_ROUTING_SEARCH_KEY 属性集中为它们分配字符串名称, 这些名称不会干扰给定给任何核心可映射属性的名称。 例如, 假设客户端需要在长路由列表中传输包含最后一个用户的搜索关键字的属性。 客户端可以在 PS_ROUTING_SEARCH_KEY 属性集中创建名为 "last_search_key" 的命名属性。 因为它存储在一个不可映射的属性集中, 所以 "last_search_key" 属性将与其他的网关映射属性一起转换。
  

