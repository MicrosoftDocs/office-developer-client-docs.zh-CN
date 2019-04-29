---
title: 使用 MAPI 发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3edfbfff-ea15-4926-bf0f-47137251d921
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf6324b89f06ef7f0553d3de1eaa24ae31a329ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438720"
---
# <a name="sending-messages-by-using-mapi"></a>使用 MAPI 发送邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端应用程序调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法以发送邮件。 **SubmitMessage**调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)以在将控制转移到 MAPI 后台处理程序或直接转到传输提供程序之前保存邮件。 
  
如果发生以下任一情况, MAPI 后台处理程序将收到邮件:
  
- 邮件存储区提供程序和传输提供程序未紧密结合。
    
- 邮件需要进行预处理。
    
- 紧密耦合邮件存储和传输无法处理邮件所针对的所有收件人。
    
紧密耦合邮件存储必须先考虑邮件的状态, 然后才能将其显示到要下载到传输提供程序的 MAPI 后台处理程序。 在某些情况下, 可能会出现需要 mapi 后台处理程序的邮件, 但实际上不会涉及 mapi 后台处理程序。
  
例如, 考虑用户从收件箱提交邮件的情况。 客户端使用紧密耦合的存储和传输。 如果紧耦合邮件存储区使用邮件的位置作为确定是否允许 mapi 后台处理程序处理邮件的唯一条件, MAPI 后台处理程序将始终接收邮件。 若要避免这种问题, 紧耦合邮件存储区必须先检查邮件状态以及邮件位置。 特别是, 传输提供程序不应请求 MAPI 后台处理程序下载任何主动提交的邮件。
  
邮件传输过程涉及邮件存储提供程序、一个或多个传输提供程序和 MAPI。 本节中的主题提供有关邮件传输过程中特定角色的详细信息。
  
## <a name="see-also"></a>另请参阅



[IMessage::SubmitMessage](imessage-submitmessage.md)
  
[IMAPIProp::SaveChanges](imapiprop-savechanges.md)

