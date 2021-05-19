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
  
客户端必须遵循需要由网关转换的属性的命名约定。 所有要转换的属性都应创建为指定为保留可映射属性的五个属性集之一中的命名属性：
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
PS_ROUTING_SEARCH_KEY
  
必须为与同一用户相关的寻址属性指定相同的名称。 网关依赖于此命名约定，这使它们能够将地址与正确的地址类型相匹配。 对于地址分析，地址和地址类型之间的映射必须准确。
  
MAPI 命名属性用 **MAPINAMEID** 数据结构表示，该结构指定属性名称可以是 Unicode 字符串或 32 位整数。 有关详细信息，请参阅 [MAPINAMEID](mapinameid.md)。 建议对地址组使用整数命名，因为它是区分可映射属性集的一种简单方法，并且可以轻松地用作用户的索引。 使用整数的替代方法是分配一个字符串作为用户的所有五个可映射属性的名称。 如果只有一个用户需要映射，则分配字符串是可接受的。 但是，当存在多个用户时，最好使用整数命名。 名称（无论是基于数字还是基于字符串）应存储在特定于邮件类的属性中，或存储在属于客户端应用程序定义的属性集的属性中。 
  
> [!NOTE]
> 避免将整数名称转换为字符串，例如"route_recipient_1"和"route_recipient_2"。 无需进行此工作。 
  
若要说明此命名约定的工作原理，请考虑一个路由应用程序，该应用程序向四人团队的每个成员发送消息。 当一个成员收到邮件时，他/她必须先响应该邮件，然后才能将邮件连同已编译的响应一起发送给下一个成员。 原始邮件包含一个收件人列表，其中包含一个条目：团队的第一个成员。 邮件中嵌入了其他三个团队成员的网关可映射属性。 每个成员都有五个核心用户属性，这些属性驻留在网关可映射属性集内，这些属性分配有一个唯一的号码作为名称。 
  
下表演示了为其余三个工作组成员存储的网关可映射属性集的设置，当第一个团队成员处理完邮件后，邮件将路由到这些团队成员。
  
|**Property Set**|**Second Team  <br/> Member**|**第三  <br/> 个团队成员**|**第四  <br/> 个团队成员**|
|:-----|:-----|:-----|:-----|
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |Address = 0  <br/> |Address = 1  <br/> |地址 = 2  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |地址类型 = 0  <br/> |地址类型 = 1  <br/> |地址类型 = 2  <br/> |
|PS_ROUTING_DISPLAY_NAME  <br/> |显示名称 = 0  <br/> |显示名称 = 1  <br/> |显示名称 = 2  <br/> |
|PS_ROUTING_ENTRYID  <br/> |条目标识符 = 0  <br/> |条目标识符 = 1  <br/> |条目标识符 = 2  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |搜索键 = 0  <br/> |搜索键 = 1  <br/> |搜索键 = 2  <br/> |
   
使用可映射搜索键作为对其他邮件属性的引用的客户端必须识别其他邮件属性将不会转换，除非它们被放置在这些可映射属性集之一中。 将具有对映射搜索键的未映射引用的邮件发送到另一个邮件域中的目标时，引用无效。 若要使这些其他属性与搜索键保持同步，可以在 PS_ROUTING_SEARCH_KEY 属性集内为其分配字符串名称，该字符串名称不会干扰为任何核心可映射属性提供的名称。 例如，假设客户端需要传输包含长路由列表中最后一个人搜索密钥的属性。 客户端可以在名为"last_search_key"的 PS_ROUTING_SEARCH_KEY 属性集内创建命名属性。 由于它存储在可映射属性集内，因此"last_search_key"属性与网关可映射属性的其余部分一起转换。
  

