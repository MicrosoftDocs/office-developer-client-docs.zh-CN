---
title: 使用 HTML 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3edfbfff-ea15-4926-bf0f-47137251d921
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 36de3b70b0ab7b16f8abed85bbd0983224e00568
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778735"
---
# <a name="sending-messages-by-using-mapi"></a>使用 HTML 发送邮件

  
  
**适用于**： Outlook 
  
客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法发送消息。 **SubmitMessage**调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)保存邮件之前将控制转到以下任意 MAPI 后台处理程序或直接到传输提供程序。 
  
如果发生下列任一情况，MAPI 后台处理程序接收的消息：
  
- 未紧密耦合的消息存储提供程序和传输提供程序。
    
- 邮件需要预处理。
    
- 紧密耦合的消息存储和传输无法处理所有向其发送邮件的收件人。
    
紧密耦合的消息存储必须考虑邮件状态之前其呈现给 MAPI 后台处理程序下载到传输提供程序。 有其中显示一条消息，可能需要 MAPI 后台处理程序，但 MAPI 后台处理程序应真正不涉及的情况。
  
例如，假设其中用户提交收件箱中的邮件的情况。 客户端使用紧密耦合的存储和传输。 如果紧密耦合的消息存储使用的消息的位置用作唯一条件来决定允许 MAPI 后台处理程序有关处理邮件，MAPI 后台处理程序始终会收到消息。 若要避免这种类型的问题，紧密耦合的消息存储必须检查邮件状态除了邮件位置。 具体而言，传输提供程序不应请求 MAPI 后台处理程序下载主动提交任何消息。
  
邮件传输过程涉及的消息存储提供程序、 一个或多个传输提供程序和 MAPI。 本节中的主题提供有关邮件传输过程中的特定角色的详细的信息。
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)

