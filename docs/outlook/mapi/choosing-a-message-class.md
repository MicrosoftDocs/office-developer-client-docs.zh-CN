---
title: 选择邮件类别
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ca8edd2-41b7-40e2-b755-b28eecb49786
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 279df7f07c8c8b66347488c6224d04f70292e968
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285256"
---
# <a name="choosing-a-message-class"></a>选择邮件类别

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如[MAPI 消息类](mapi-message-classes.md)中所述, 邮件类对于在表单服务器本身之间建立自定义邮件类型和扩展之间的关系非常重要。 幸运的是, 选择邮件类字符串相当简单。 邮件类的邮件类字符串是任意字符串, 但它应使用以下约定:
  
- 该字符串应满足**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性的文档中所述的所有约定。 重要的是, 该字符串必须完全由 ANSI 字符组成, 并且长度不超过256个字符。
    
- 如果您的表单服务器是从现有表单服务器派生的, 或者是现有表单服务器的扩展, 则应通过向您的表单所基于的表单服务器的邮件类字符串添加一个句点和另一个词来形成您的邮件类字符串。 例如, 您可能希望实施一个表单以重新安排会议, 而您的表单基于现有表单来安排会议。 如果会议计划表单的邮件类字符串为 "IPM。会议 ", 您的邮件类字符串可能是" IPM。会议 "重新安排"。
    
- 如果窗体不基于任何现有的窗体, 则邮件类字符串仍应以 "IPM" 开头。 或 "IPC"。 前缀, 具体取决于窗体是供用户接收还是由其他应用程序接收。 "IPM." 指定通常在用户的收件箱中结束的人际邮件和 "IPC"。 指定通常不传递到用户收件箱的进程间通信消息。
    
- 如果您的邮件类可供人工阅读, 则邮件类字符串应以 "IPM." 开头。 如果邮件类别使用任何包含纯文本、HTML 或 rtf 格式 (rtf) 数据的属性, 通常会将邮件类别视为可读邮件。 如果您的表单使用**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性, 则几乎一定要使用 "IPM"。 邮件类字符串。 例如, 如果您要为采购订单实施一个表单, 并且您的组织要求由经理批准该采购订单, 则您的邮件类字符串可能是 "IPM。Purchase_Order "。 设计为与公用文件夹或公用文件夹应用程序一起使用的表单通常被视为 "人际", 因为他们会被人阅读, 即使它们实际上并不是发往任何人的电子邮件地址。 公用文件夹邮件类别的典型前缀是 "IPM。Post "。 
    
- 如果您的邮件类打算由另一个应用程序而不是某人接收, 则邮件类字符串应以 "IPC" 开头。 例如, 如果您要实现一个使用户能够自动订阅邮件列表的表单, 则邮件类字符串可能为 "IPC。订阅 "。
    
- 您的邮件类字符串永远不应以句点结尾。
    
邮件类字符串应放在表单配置文件的 "**说明**" 部分的 " **MessageClass** " 条目中, 如下所示: 
  
 `MessageClass=IPM.Meeting.Reschedule`
  
选择适当的邮件类字符串后, 应为其生成类标识符。 可以使用 Visual Studio 中包含的**Create GUID**命令生成类标识符。 类标识符必须放在表单配置文件的**CLSID**条目中, 以及**MessageClass**条目, 如下所示: 
  
 `CLSID={88FFF551-B8C5-11ce-8DE0-00AA0060D242}`
  
当然, 您的类标识符几乎也是不同的。 有关详细信息, 请参阅[创建表单配置文件](creating-a-form-configuration-file.md)。
  
当表单安装在用户计算机上时, 您的安装过程 (无论是安装程序还是其他内容) 必须在注册表的 **HKEY_CLASSES_ROOT\CLSID\* *部分中为类标识符生成一个注册表项。 此条目必须设置为邮件类字符串。 例如, 您可以为上面的示例类标识符创建类似于以下的注册表项: 
  
 `HKEY_CLASSES_ROOT\CLSID\{88FFF551-B8C5-11ce-8DE0-00AA0060D242}="IPM.Meeting.Reschedule"`
  
有关详细信息, 请参阅将[表单安装到库](installing-a-form-into-a-library.md)中。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

