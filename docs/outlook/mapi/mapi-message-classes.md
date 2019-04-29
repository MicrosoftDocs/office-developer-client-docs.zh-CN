---
title: MAPI 邮件类别
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 64ef2bbb-585c-4908-8ad4-a1c954057e9b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b2ab5d56c53216152a83ca207ff5ba1d53c9049d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412084"
---
# <a name="mapi-message-classes"></a>MAPI 邮件类别

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每封邮件都有一个消息类属性**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)), 该属性标识邮件的类型、目的或内容。 **PR_MESSAGE_CLASS**是所有新邮件的必需属性。 邮件的类决定了用于向用户显示邮件的窗体和用于放置传入邮件的文件夹。 
  
邮件类是区分大小写的字符字符串, 其中包含 ASCII 字符32到127并由句点分隔, 但不能以句点结尾。 每个字符串表示一个级别的子类, 并且对允许的级别数没有限制。 
  
例如, 客户端应用程序发送和接收的大多数邮件都属于**IPM**邮件类, 这是一个描述所有人际邮件 (即应由人为用户阅读的邮件, 而不是以编程方式通过计算机)。 邮件存储提供程序通过创建**ipm**子类更准确地描述 ipm 邮件。 **ipm**子类继承了**ipm**邮件类的属性。 **ipm**类的子类通过将其他字符字符串串联到 ipm 标识符 (如 ipm) 来命名 **。注释**: 说明注释消息和**IPM。联系**以描述联系人消息。 
  
若要处理 IPM 邮件的显示和管理, 客户端可以使用 MAPI 提供的标准表单。 若要处理新邮件类的显示和管理, 您作为客户端应用程序开发人员有两个选项:
  
1. 您可以使用标准客户端可以使用的由 MAPI 定义的表单界面集来创建新的表单。
    
2. 您可以通过实现完整的独立应用程序来编写自己的客户端。 
    
虽然客户端应将每个传出邮件的**PR_MESSAGE_CLASS**属性设置为**IPM**或**IPC**的子类, 但邮件存储区提供程序对设置它的最终责任是最大的。 因此, 如果客户端发送邮件时未设置其邮件类别, 则邮件存储提供程序会将其设置为适当类型的客户端的相应默认值。 人际邮件客户端的默认邮件类为**IPM**;进程间通信客户端的默认邮件类为**IPC**。 
  
邮件类别的长度限制为255个字符。 但是, 邮件类别不应超过127个字符以支持在报告中使用的邮件类。 报告邮件类基于原始邮件的类, 其中包含两个添加项: 前缀和后缀。 前缀报告指示邮件是一个报告, 后缀指示报告类型: DR (传递报告)、NDR (nondelivery report)、IPNRN (read report) 或 IPNNRN (未读 report)。 请注意, 这些长度限制是在字符中提供的;在使用双字节字符集的平台上, 实际字节计数可能会更高。 
  
当客户端尝试分配超过其邮件类别允许的限制的字符串时, 邮件存储提供程序应从其[IMAPIProp:: SetProps](imapiprop-setprops.md)方法实现中返回 MAPI_E_INVALID_PARAMETER。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

