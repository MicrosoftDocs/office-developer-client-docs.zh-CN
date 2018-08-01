---
title: 选择邮件类别
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ca8edd2-41b7-40e2-b755-b28eecb49786
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f1e604120041e9d91d06276fabb2e9dd7505df51
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774685"
---
# <a name="choosing-a-message-class"></a>选择邮件类别

  
  
**适用于**： Outlook 
  
如[MAPI 邮件类](mapi-message-classes.md)中所述，邮件类很重要建立类型的自定义消息，并按扩展名，他们自己的窗体服务器之间的关系。 幸运的是，选择消息类字符串是相当简单。 邮件类的邮件类字符串的任意字符串，但它应使用以下约定：
  
- 字符串应满足所有**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性文档中所述的约定。 重要的是，该字符串必须完全组成 ANSI 字符，为长度小于 256 个字符。
    
- 如果您的窗体服务器派生自现有表单服务器或是一种扩展的现有的窗体服务器，则邮件类字符串应通过将一个句点和另一个单词添加到表单服务器表单所基于的邮件类字符串格式正确。 例如，您可能希望实现的窗体重新计划会议，并且表单基于现有表单安排会议。 如果会议安排窗体的邮件类字符串是"IPM。会议"，则邮件类字符串可以是"IPM。Meeting.Reschedule"。
    
- 如果窗体不基于任何现有的窗体，则邮件类字符串应仍开头任一"IPM。" 或者"IPC。" 前缀，具体取决于是否窗体旨在接收由人员或另一个应用程序。 "IPM。" 指定一人际邮件，其中通常中的最终用户的收件箱中和"IPC。" 指定通常未发送给用户的收件箱进程间通信消息。
    
- 如果您的邮件类用于为可读，消息类字符串应开头"IPM。" 邮件类通常被视为可读如果它使用所有包含纯文本、 HTML 属性或富文本格式 (RTF) 数据。 如果表单使用**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，它应几乎可以使用"IPM。" 邮件类字符串。 例如，如果要实现的采购订单表单，并且您的组织需要采购订单将经管理员，您的邮件类字符串可以是"IPM。Purchase_Order"。 为设计的窗体使用公用文件夹或公用文件夹应用程序通常被视为是人际，由于它们读取的人员，即使它们不实际寻址到任何人的电子邮件地址。 公用文件夹的邮件类的典型前缀是"IPM。文章"。 
    
- 如果您的邮件类用于由人员接收的而不是另一个应用程序，消息类字符串应开头"IPC。" 例如，如果要实现，使人们能够自动订阅邮件列表窗体，则邮件类字符串可以是"IPC。订阅"。
    
- 您的邮件类字符串应永远不会以句点结尾。
    
邮件类字符串应置于中**MessageClass**条目，类似于以下的窗体配置文件的 **[描述]** 部分： 
  
 `MessageClass=IPM.Meeting.Reschedule`
  
您已选择相应的消息类字符串后，您应为其生成的类标识符。 可以使用包含在 Visual Studio 中**创建 GUID**命令生成的类标识符。 必须在窗体配置文件的**CLSID**项，以及该**MessageClass**条目，类似于以下放置的类标识符： 
  
 `CLSID={88FFF551-B8C5-11ce-8DE0-00AA0060D242}`
  
您的类标识符几乎可以将不同，当然。 有关详细信息，请参阅[创建窗体配置文件](creating-a-form-configuration-file.md)。
  
在安装过程的用户的计算机上安装该窗体的时 — 是否安装程序或其他内容 — 必须进行中的注册表项 **HKEY_CLASSES_ROOT\CLSID\** 部分中的类标识符的注册表。 此条目必须设置为邮件类字符串。 例如，将创建一个注册表项与上面的示例类标识符的以下内容类似： 
  
 `HKEY_CLASSES_ROOT\CLSID\{88FFF551-B8C5-11ce-8DE0-00AA0060D242}="IPM.Meeting.Reschedule"`
  
有关详细信息，请参阅[安装到库窗体](installing-a-form-into-a-library.md)。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

