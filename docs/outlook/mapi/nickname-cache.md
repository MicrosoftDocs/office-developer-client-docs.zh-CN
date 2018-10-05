---
title: 别名缓存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2813c102-6778-4443-ab4b-b573f3568705
description: 上次修改时间： 2013 年 1 月 30 日
ms.openlocfilehash: 841b01ae8dfcf841b0a1d64113ce7258c4c61583
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389258"
---
# <a name="nickname-cache"></a>别名缓存

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Office Outlook 2007、 Microsoft Outlook 2010 和 Microsoft Outlook 2013 交互昵称缓存，也称为"记忆式键入流。" 记忆式键入流是 Outlook 仍然存在记忆式键入列表，这是在**到**、**抄送**，显示名称的列表和**密件抄送**编辑框时用户撰写电子邮件时的位置。 本主题介绍 Outlook 2007、 Outlook 2010 和 Outlook 2013 如何记忆式键入流交互，并讨论该文件，用于与记忆式键入流进行交互的建议的方式的二进制格式。 
  
对于 Outlook 2010 或 Outlook 2013 与之交互的应用程序，记忆式键入流存储为 MAPI 属性，可以使用 MAPI 或邮件的**PropertyAccessor**对象进行修改。 Outlook 2010 或 Outlook 2013 对象模型中公开**PropertyAccessor**对象。 
  
没有依赖 Outlook 2007 对象模型或 MAPI Api。 因此，可以使用任何编程语言编写的应用程序对 Outlook 2007 中的记忆式键入流进行更改。
  
## <a name="interacting-with-the-autocomplete-stream"></a>与记忆式键入流交互

**到**、**抄送**或**密件抄送**编辑框访问上一条消息时, 记忆式键入流加载和显示用户的用户名的列表。 Outlook 与以下两种方式记忆式键入流进行交互： 
  
1. 加载记忆式键入流 
    
2. 将更改保存到记忆式键入流中的数据
    
存储记忆式键入数据的方式与 Outlook 2007 和 Outlook 2010 或 Outlook 2013 之间，如下所示： 
  
 **Outlook 2007**
  
为 Outlook 2007 记忆式键入流存储在具有相同名称配置文件和.nk2 扩展名的文件。 例如，如果使用的"outlook"的默认配置文件，则该文件将调用"outlook.nk2"。 .Nk2 文件存储在 %appdata%\microsoft\outlook。 有关昵称缓存二进制文件格式的详细信息，请参阅[Outlook 2003/2007 NK2 文件格式和开发人员的准则](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。
  
 **Outlook 2010 和 Outlook 2013**
  
Outlook 2010 或 Outlook 2013 中从关联的内容表中的邮件帐户的传递存储区的收件箱中的邮件读取记忆式键入流。 此隐藏的邮件具有邮件类和 IPM 的主题。Configuration.Autocomplete。 记忆式键入流 PR_ROAMING_BINARYSTREAM 属性 （[PidTagRoamingBinary 规范属性](pidtagroamingbinary-canonical-property.md)） 中的此邮件上存储。 Autocomplete 数据可能会临时缓存位于 %userprofile%\appdata\local\microsoft\outlook\roamcache 记忆式键入.dat 文件中。 但是，.dat 文件是仅缓存，并且不用于在用户退出 Outlook 2010 或 Outlook 2013 时，回写到传递存储区。
  
## <a name="loading-the-autocomplete-stream"></a>加载记忆式键入流

Outlook 加载记忆式键入流，当初始化具有寻址的功能的项。 例如，新邮件、 邮件答复、 联系人项目、 会议请求中，依次类推中使用电子邮件地址。 若要加载的数据，Outlook 将 stream 的内容的所有读入内存。
  
记忆式键入操作的 Outlook 进行交互以独占方式使用该内存中结构 outlook.exe 进程的生存期内的持续时间内。 Outlook 仅保存在关闭的结构。 在此过程，请参阅下一节"保存记忆式键入流"的详细信息。
  
## <a name="saving-the-autocomplete-stream"></a>保存记忆式键入流

如果记忆式键入列表中任何通过以下方式已更改，则 outlook 将在关闭保存记忆式键入流：
  
- 通过解析名称、 选取通讯簿对话框中，从收件人或将邮件发送给收件人列表中已不存在添加一个新的昵称条目。
    
- 通过将邮件发送到现有收件人列表中，将修改条目。
    
- 由用户通过用户界面删除了一个条目。
    
- 其他与本主题不相关的次要方案。
    
将更改保存到记忆式键入数据涉及到[记忆式键入流](autocomplete-stream.md)重新编写内存中的结构。 当与 Outlook 2007 中交互，流被保存到本地.nk2 文件。 对于 Outlook 2010 或 Outlook 2013，记忆式键入流将写回关联的内容表中的邮件帐户的传递存储区的收件箱。
  
## <a name="recommendations"></a>建议

- 从不部分修改记忆式键入流。 支持的交互是 1） 的整个记忆式键入流读取到内存和 2） 修改的内存结构，3） 整个流回写到以下任意关联的内容表中的邮件帐户的传递存储区的收件箱 (Outlook 2010 或Outlook 2013) 或本地.nk2 文件 (Outlook 2007)。
    
- 不进行交互与记忆式键入数据流运行 Outlook 时。 如果 Outlook 正在运行时修改流，它将其关闭时，可能覆盖所做的更改。
    
- 执行操作的不写入属性键入 PT_MV_UNICODE 和 PR_MV_STRING8 到要由 Microsoft Outlook 2003 记忆式键入流。 Outlook 2007、 Outlook 2010 和 Outlook 2013 仅理解这些属性。
    
- 开发与 Outlook 2007 交互的代码时，我们建议您锁定其他进程中修改的.nk2 文件时要读取和写入它使用标准文件锁定 Api (例如，**锁定文件**C/c + + 和**中FileStream.Lock**中 C#)。 
    
- 只能修改从记忆式键入流行集中的类型的属性。 有关记忆式键入流属性和属性类型的详细信息，请参阅[记忆式键入流](autocomplete-stream.md)。
    
## <a name="see-also"></a>另请参阅



[自动完成流](autocomplete-stream.md)
  
[MAPI 配置文件](mapi-profiles.md)


[Outlook 2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)

