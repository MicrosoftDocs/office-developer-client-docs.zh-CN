---
title: MAPI 邮件类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 64ef2bbb-585c-4908-8ad4-a1c954057e9b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: eecbbb3b806ecaee6c7ceba5c92bd4b713ad1075
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575138"
---
# <a name="mapi-message-classes"></a>MAPI 邮件类

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
每个邮件具有邮件类属性， **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))，它标识类型、 目的或消息的内容。 **PR_MESSAGE_CLASS**是必需的属性对所有新邮件。 邮件类决定用于向用户和发出传入消息的文件夹的邮件的形式。 
  
邮件类是区分大小写的字符串，包含 ASCII 字符到 127 32 和用句点，分隔，但他们不能以句点结尾。 每个字符串表示的子类，级别和允许的级别数为没有限制。 
  
例如，最多邮件客户端应用程序发送和接收分为**IPM**邮件类时，广，它介绍了所有人际邮件 (也就是说，为了按人员的用户，而不是以编程方式通过读取的消息计算机）。 消息存储提供程序更精确地介绍了通过创建**IPM**子类的 IPM 消息。 **IPM**子类继承**IPM**邮件类的属性。 通过连接到 IPM 标识符，如**IPM 其他字符的字符串被命名**IPM**类的子类。注意**来描述说明消息和**IPM。联系人**描述联系人的邮件。 
  
若要处理的显示和管理 IPM 消息，客户端可以使用 MAPI 提供了对标准窗体。 若要处理的显示和管理新的邮件类，您作为客户端应用程序开发人员具有两个选项：
  
1. 通过使用标准的客户端可以使用的 MAPI 定义窗体接口的组，可以创建新表单。
    
2. 您可以编写自己的客户端通过实施一个完整、 独立的应用程序。 
    
客户端应将每个传出 message **PR_MESSAGE_CLASS**属性设置为**IPM**或**IPC**的一个子类，尽管消息存储提供程序具有其设置的 ultimate 责任。 因此，如果客户端发送一条消息，而不设置其邮件类别，消息存储提供程序将其设置为适当的客户端类型的适当的默认值。 人际邮件客户端的默认邮件类别是**IPM**;进程间的通信客户端的默认邮件类别是**IPC**。 
  
邮件类具有长度限制为 255 个字符。 但是，邮件类不应超过 127 个字符，以支持报告中所使用的邮件类。 报告邮件类基于的原始邮件，两个内容类： 前缀和后缀。 前缀报告指示邮件是报表，并且后缀指示的报告类型： 灾难恢复 （送达报告）、 NDR （原件报告）、 IPNRN （阅读报告） 或 IPNNRN （nonread 报告）。 请注意，这些长度限制授予以字符;使用双字节字符集的平台上, 实际的字节数可能更高版本。 
  
客户端尝试分配的字符串超出其邮件类别的允许限制时，消息存储提供程序应从其[IMAPIProp::SetProps](imapiprop-setprops.md)方法实现返回 MAPI_E_INVALID_PARAMETER。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

