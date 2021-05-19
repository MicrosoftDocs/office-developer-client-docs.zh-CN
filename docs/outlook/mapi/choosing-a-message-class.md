---
title: 选择邮件类
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 5ca8edd2-41b7-40e2-b755-b28eecb49786
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 279df7f07c8c8b66347488c6224d04f70292e968
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428051"
---
# <a name="choosing-a-message-class"></a>选择邮件类

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如 [MAPI 邮件类中所述](mapi-message-classes.md)，邮件类对于在自定义邮件类型之间以及表单服务器本身（按扩展名）之间建立关系非常重要。 幸运的是，选择邮件类字符串相当简单。 邮件类的邮件类字符串是任意字符串，但它应使用以下约定：
  
- 该字符串应满足文档中介绍的所有约定，如 PR_MESSAGE_CLASS ( [PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。 重要的是，字符串必须完全由 ANSI 字符组成，且长度必须少于 256 个字符。
    
- 如果您的表单服务器派生自现有表单服务器或现有表单服务器的扩展，则应该通过向表单所基于的表单服务器的邮件类字符串添加句点和另一个单词来形成邮件类字符串。 例如，您可能希望实现一个表单来重新安排会议，并且您的表单基于用于安排会议的现有表单。 如果会议安排表单的邮件类字符串为"IPM"。Meeting，你的邮件类字符串可能是"IPM"。Meeting.Reschedule"。
    
- 如果您的表单不基于任何现有表单，则邮件类字符串仍应该以"IPM"开头。 或"IPC"。 前缀，具体取决于表单是供人员接收还是由另一个应用程序接收。 "IPM"。 指定通常以用户收件箱结尾的外向邮件和"IPC"。 指定通常不传递到用户收件箱的进程间通信邮件。
    
- 如果邮件类是可人工读取的，则邮件类字符串应以"IPM"开头。 如果邮件类使用包含 RTF 格式的纯文本、HTML 或 RTF 格式的任何属性，则通常 (可读) 数据。 如果您的表单使用 PidTagBody **PR_BODY (** [PidTagBody](pidtagbody-canonical-property.md)) ，它几乎一定使用"IPM"。 message 类字符串。 例如，如果要为采购订单实现表单，并且您的组织要求经理批准采购订单，则邮件类字符串可以是"IPM"。Purchase_Order"。 设计为与公用文件夹或公用文件夹应用程序一同使用的表单通常被视为一种社会性表单，因为它们由用户读取，即使它们实际上并未寻址到任何人的电子邮件地址。 公用文件夹邮件类的典型前缀为"IPM"。Post"。 
    
- 如果邮件类由另一个应用程序而不是人员接收，则邮件类字符串应以"IPC"开头。 例如，如果要实现使用户能够自动订阅邮件列表的窗体，则邮件类字符串可以是"IPC"。订阅"。
    
- 您的邮件类字符串永远不应以一个时间段结尾。
    
邮件类字符串应放在表单配置文件的 **[Description]** 部分中的 **MessageClass** 条目中，类似于以下内容： 
  
 `MessageClass=IPM.Meeting.Reschedule`
  
选择适当的邮件类字符串后，应生成其类标识符。 类标识符可以使用包含在 Visual Studio 中的 **Create GUID** 命令生成。 类标识符必须与 **MessageClass** 条目一起放在表单配置文件的 **CLSID** 条目中，如下所示： 
  
 `CLSID={88FFF551-B8C5-11ce-8DE0-00AA0060D242}`
  
当然，你的类标识符几乎肯定不同。 有关详细信息，请参阅 [创建表单配置文件](creating-a-form-configuration-file.md)。
  
在用户计算机上安装表单时，您的安装过程（无论是安装程序还是其他过程）必须在注册表的 **HKEY_CLASSES_ROOT\CLSID\** 部分中为类标识符创建注册表项。 此项必须设置为邮件类字符串。 例如，您将为上述示例类标识符创建类似于下面的注册表项： 
  
 `HKEY_CLASSES_ROOT\CLSID\{88FFF551-B8C5-11ce-8DE0-00AA0060D242}="IPM.Meeting.Reschedule"`
  
有关详细信息，请参阅 [将窗体安装到库中](installing-a-form-into-a-library.md)。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

