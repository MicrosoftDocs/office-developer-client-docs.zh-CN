---
title: MAPI 邮件类
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
# <a name="mapi-message-classes"></a>MAPI 邮件类

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每封邮件都有一个 message类属性PR_MESSAGE_CLASS ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) ，用于标识邮件的类型、用途或内容。 **PR_MESSAGE_CLASS** 是所有新邮件的必需属性。 邮件类确定用于向用户显示邮件的窗体和用于放置传入邮件的文件夹。 
  
邮件类是区分大小写的字符串，其中包含 32 到 127 的 ASCII 字符，并且由句点分隔，但它们不能以句点结尾。 每个字符串表示一个子类级别，对允许的级别数没有限制。 
  
例如，客户端应用程序发送和接收大多数邮件都属于 **IPM** 邮件类，这是一个广泛的类别 (它描述所有不法邮件 (即，打算由用户而不是计算机用户以编程方式读取) 的邮件。 邮件存储提供程序通过创建 IPM 子类来更精确地描述 **IPM** 邮件。 **IPM** 子类继承 **IPM** 邮件类的属性。 **IPM** 类的子类通过连接其他字符串到 IPM 标识符（如 **IPM）来命名。用于** 描述便笺消息和 **IPM 的注释。用于** 描述联系人邮件的联系人。 
  
若要处理 IPM 消息的显示和管理，客户端可以使用 MAPI 提供的标准窗体。 若要处理新邮件类的显示和管理，作为客户端应用程序开发人员，您具有两个选项：
  
1. 可以使用标准客户端可以使用的 MAPI 定义的表单接口集来创建新表单。
    
2. 可以通过实现完整的独立应用程序来编写自己的客户端。 
    
尽管客户端应该将每个传出PR_MESSAGE_CLASS的属性设置为 IPM 或 **IPC** 的子类，但邮件存储提供程序对设置它具有最终责任。 因此，如果客户端在未设置其邮件类的情况下发送邮件，则邮件存储提供程序会将其设置为适当类型的客户端的适当默认值。 邮件客户端的默认邮件类别为 **IPM**;进程间通信客户端的默认消息类是 **IPC**。 
  
邮件类的长度限制为 255 个字符。 但是，邮件类不应超过 127 个字符以支持报告中使用的邮件类。 报告邮件类基于原始邮件的类，并添加两个：前缀和后缀。 前缀 REPORT 指示邮件是报告，后缀指示报告类型：DR (送达报告) 、NDR (未送达报告) 、IPNRN (阅读报告) 或 IPNNRN (未读报告) 。 请注意，这些长度限制以字符表示;在使用双字节字符集的平台上，实际的字节计数可能更高。 
  
当客户端尝试分配超过其邮件MAPI_E_INVALID_PARAMETER的允许限制的字符串时，邮件存储提供程序应从 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法实现中返回值。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

