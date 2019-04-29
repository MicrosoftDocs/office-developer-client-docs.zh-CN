---
title: 邮件提交模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bcd19f6-c225-43ac-8c27-c46388e9097a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 090a765fd6c758e5f146caa0e7f36276b052f69e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421121"
---
# <a name="message-submission-model"></a>邮件提交模型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件提交是通过从 MAPI 后台处理程序到传输提供程序的一系列调用来完成的。 这些调用的序列化如下所示:
  
1. MAPI 后台处理程序调用[IXPLogon:: SubmitMessage](ixplogon-submitmessage.md), 传入[IMessage: IMAPIProp](imessageimapiprop.md)实例, 以开始该过程。 
    
2. 然后, 传输提供程序将引用值 (在以后引用此邮件时使用的传输定义标识符) 放在**SubmitMessage**中引用的位置。
    
3. 传输提供程序使用传递的**IMessage**实例访问邮件数据。 对于为其接受责任的传递的**IMessage**中的每个收件人, 传输提供程序将设置**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性, 然后返回。
    
4. 传输提供程序可以使用[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法来指示它是识别无法传递到的所有收件人, 还是要创建一个标准送达报告。 对于已确定某些收件人无法传递到或已收到用户或客户端应用程序可能的基础邮件系统中的传递信息的传输提供程序, **StatusRecips**是很方便的。查找有用的。 
    
5. mapi 后台处理程序对[IXPLogon:: EndMessage](ixplogon-endmessage.md)的调用是最终职责, 即从 MAPI 后台处理程序到传输提供程序的邮件。 
    
6. MAPI 后台处理程序可以使用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)在**SubmitMessage**或**EndMessage**调用过程中取消邮件处理。 
    

