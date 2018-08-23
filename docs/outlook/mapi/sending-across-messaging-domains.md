---
title: 跨消息传递域发送
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 65594253-66cd-486a-aa5b-0bc719f761f0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 40c12a4010d51cb433b62558b5fe1d12afb583dd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567066"
---
# <a name="sending-across-messaging-domains"></a>跨消息传递域发送

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
消息域表示共享通用的地址格式的一个或多个邮件系统。 跨多个邮件的域的通信涉及转换到的目标消息域格式的原始消息域格式发送一条消息。 因为并非所有地址格式兼容，网关需要翻译的目标格式的源格式的寻址信息。 若要确保跨消息的域的有效性，客户端应用程序中 MAPI 属性存储寻址的重要信息。 此外，网关执行翻译，并检查属性已知需要翻译并将其更改为目标消息域可以使用的格式。
  
以前，MAPI 允许此寻址信息与仅包含一条消息的当前收件人列表的用户相关联。 描述每个成员的收件人列表的属性由网关以确保整个邮件的域的有效性发生了所需的转换。 但是，某些应用程序需要其邮件包含解决可能已过去的收件人的用户信息、 将来，将收件人或永远不会收件人。 例如，路由应用程序，按指定顺序向组发送邮件的用户，在消息中嵌入寻址这些用户信息。 嵌入的信息通常包括的地址和将来的收件人，或许还他们的角色和路由的顺序，其名称和每个收件人的一个或多个二进制标识符中的位置的地址类型。
  
若要启用邮件，其中包含有关这些 nonrecipient 用户信息，MAPI，现在包括用于确保此 nonrecipient 信息还跨消息域的正确转换的策略。 此策略取决于网关可映射属性的概念。
  

