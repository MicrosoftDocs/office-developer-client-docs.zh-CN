---
title: 别名缓存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2813c102-6778-4443-ab4b-b573f3568705
description: 上次修改时间：2013 年 1 月 30 日
ms.openlocfilehash: 841b01ae8dfcf841b0a1d64113ce7258c4c61583
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334515"
---
# <a name="nickname-cache"></a>别名缓存

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Office Outlook 2007、Microsoft Outlook 2010 和 Microsoft Outlook 2013 与昵称缓存交互，也称为"自动完成流"。 自动完成流是 Outlook保留自动完成列表的位置，该列表是用户在撰写电子邮件时显示在"To"、Cc 和 **"Bcc"** 编辑框中的名称列表。 本主题介绍 Outlook 2007、Outlook 2010 和 Outlook 2013 如何与自动完成流交互，并讨论文件的二进制格式以及与自动完成流交互的建议方法。 
  
对于与 Outlook 2010 或 Outlook 2013 交互的应用程序，自动完成流存储为 MAPI 属性，并且可以使用邮件的 MAPI 或 **PropertyAccessor** 对象进行修改。 **PropertyAccessor** 对象在 Outlook 2010 或 Outlook 2013 对象模型中公开。 
  
2007 对象模型Outlook MAPI API 没有依赖关系。 因此，在 2007 Outlook自动完成流的应用程序可以使用任何编程语言编写。
  
## <a name="interacting-with-the-autocomplete-stream"></a>与自动完成流交互

在邮件 **上** 访问"收件人"、"抄送"或"**密** 件抄送"编辑框时，将加载自动完成流并显示用户名列表。 Outlook两种方式与自动完成流交互： 
  
1. 加载自动完成流 
    
2. 保存对自动完成流中数据的更改
    
存储自动完成数据的方式在 Outlook 2007 和 Outlook 2010 或 Outlook 2013 之间有所不同，如下所示： 
  
 **Outlook 2007**
  
对于 Outlook 2007，自动完成流存储在与配置文件同名且扩展名为 .nk2 的文件中。 例如，如果使用默认配置文件"outlook"，则该文件将被称为"outlook.nk2"。 .nk2 文件存储在 %APPDATA%\Microsoft\Outlook。 有关昵称缓存二进制文件格式的信息，请参阅 Outlook [2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。
  
 **Outlook 2010 和 Outlook 2013**
  
Outlook 2010 或 Outlook 2013 从邮件帐户传递存储的"收件箱"的"关联内容"表中的邮件读取自动完成流。 此隐藏邮件包含邮件类别和IPM.Config消息。自动完成。 自动完成流存储在此消息的 PR_ROAMING_BINARYSTREAM 属性 ([PidTagRoamingBinary](pidtagroamingbinary-canonical-property.md) 规范属性) 。 自动完成数据可能临时缓存在位于 %USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache 中的自动完成 .dat 文件中。 但是，.d Outlook at 文件只是一个缓存，在用户退出 2010 或 Outlook 2013 时，不会用于写回传递存储区。
  
## <a name="loading-the-autocomplete-stream"></a>加载自动完成流

Outlook具有寻址功能的项时加载自动完成流。 例如，电子邮件地址用于新邮件、邮件答复、联系人项目、会议请求等。 若要加载数据，Outlook将流中所有的内容读取到内存中。
  
对于自动完成操作，Outlook在进程生存期内以独占方式与此内存outlook.exe交互。 Outlook关闭时仅保存结构。 有关此过程详细信息，请参阅以下"保存自动完成流"部分。
  
## <a name="saving-the-autocomplete-stream"></a>保存自动完成流

Outlook以下列任一方式更改自动完成列表时，自动完成流在关闭时保存：
  
- 通过解析姓名、从通讯簿对话框中选取收件人或向列表中尚未包含的收件人发送邮件来添加新的昵称条目。
    
- 通过向列表中的现有收件人发送邮件来修改条目。
    
- 用户通过 UI 删除条目。
    
- 与本主题不相关的其他次要方案。
    
保存对自动完成数据所做的更改涉及将内存中的结构写回 [自动完成 Stream](autocomplete-stream.md)。 与 Outlook 2007 交互时，流将保存到本地 .nk2 文件中。 对于 Outlook 2010 或 Outlook 2013，自动完成流写回邮件帐户传递存储的"收件箱"的"关联内容"表。
  
## <a name="recommendations"></a>建议

- 从不部分修改自动完成流。 支持的交互为 1，) 将整个自动完成流读取到内存中， 2) 修改内存结构，3) 将整个流写回 (for Outlook 2010 或 Outlook 2013) 的收件箱的"关联内容"表或本地 .nk2 文件 (Outlook 2007) 。
    
- 在运行自动完成流时，不要Outlook自动完成流。 如果在Outlook流时运行，则它可能会在关闭时覆盖所做的更改。
    
- 不要将类型为 PT_MV_UNICODE 的属性PR_MV_STRING8写入 Microsoft Outlook 2003 使用的自动完成流中。 这些属性仅在 2007 Outlook 2010 Outlook 2013 Outlook理解。
    
- 开发与 Outlook 2007 交互的代码时，我们建议您在使用标准文件锁定 API（例如，C/C++ 中的 **LockFile** 和 C#) 中的 **FileStream.Lock）** 读取和写入文件时锁定 .nk (2 文件，以便其他进程修改该文件。 
    
- 仅修改来自自动完成流的行集的类型的属性。 有关自动完成流属性和属性类型的信息，请参阅 [自动完成流](autocomplete-stream.md)。
    
## <a name="see-also"></a>另请参阅



[自动完成 Stream](autocomplete-stream.md)
  
[MAPI 配置文件](mapi-profiles.md)


[Outlook 2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)

