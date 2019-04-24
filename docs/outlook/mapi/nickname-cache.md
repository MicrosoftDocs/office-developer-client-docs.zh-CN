---
title: 别名缓存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2813c102-6778-4443-ab4b-b573f3568705
description: '上次修改时间: 2013 年1月30日'
ms.openlocfilehash: 841b01ae8dfcf841b0a1d64113ce7258c4c61583
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334515"
---
# <a name="nickname-cache"></a>别名缓存

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
microsoft Office Outlook 2007、microsoft outlook 2010 和 microsoft outlook 2013 与昵称缓存进行交互 (也称为 "自动完成流")。 "自动完成" 流是 Outlook 在其中保留自动完成列表, 该列表是用户撰写电子邮件时在 "**收件人**"、 **"抄送**" 和 **"密件抄送**" 编辑框中显示的名称的列表。 本主题介绍 outlook 2007、outlook 2010 和 outlook 2013 如何与自动完成流交互, 还讨论文件的二进制格式以及与自动完成流交互的建议方式。 
  
对于与 outlook 2010 或 outlook 2013 交互的应用程序, 自动完成流将存储为 mapi 属性, 并且可以使用 mapi 或邮件的**PropertyAccessor**对象进行修改。 **PropertyAccessor**对象在 outlook 2010 或 outlook 2013 对象模型中公开。 
  
Outlook 2007 对象模型或 MAPI api 没有依存关系。 因此, 可以使用任何编程语言编写对 Outlook 2007 中的自动完成流进行更改的应用程序。
  
## <a name="interacting-with-the-autocomplete-stream"></a>与自动完成流交互

当邮件上的 "**收件人**"、 **"抄送**" 或 **"密件抄送**" 编辑框被访问时, 将加载自动完成流并显示用户名列表。 Outlook 通过以下两种方式与自动完成流进行交互: 
  
1. 加载自动完成流 
    
2. 保存对自动完成流中的数据的更改
    
存储自动完成数据的方法在 outlook 2007 和 outlook 2010 或 outlook 2013 之间有所不同, 如下所示: 
  
 **Outlook 2007**
  
对于 Outlook 2007, 自动完成流存储在与配置文件同名的文件中, 扩展名为 nk2。 例如, 如果使用的是默认的 "outlook" 配置文件, 则该文件将被称为 "nk2"。 . nk2 文件存储在%APPDATA%\Microsoft\Outlook. 中。 有关昵称缓存二进制文件格式的详细信息, 请参阅[Outlook 2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)。
  
 **outlook 2010 和 outlook 2013**
  
outlook 2010 或 outlook 2013 从邮件帐户的送达存储区的 "收件箱" 的 "关联内容" 表中的邮件中读取自动完成流。 此隐藏邮件具有 IPM 的邮件类和主题。配置。自动完成。 自动完成流存储在此邮件的 PR_ROAMING_BINARYSTREAM 属性 ([PidTagRoamingBinary 规范属性](pidtagroamingbinary-canonical-property.md)) 中。 自动完成数据可能会暂时缓存在%USERPROFILE%\AppData\Local\Microsoft\Outlook\RoamCache. 中的 "自动完成" .dat 文件中。 但是, 该 .dat 文件只是一个缓存, 在用户退出 Outlook 2010 或 Outlook 2013 时不用于写回到传递存储。
  
## <a name="loading-the-autocomplete-stream"></a>加载自动完成流

每当初始化具有寻址功能的项时, Outlook 都会加载自动完成流。 例如, 电子邮件地址用于新邮件、邮件答复、联系人项目、会议请求等。 若要加载数据, Outlook 会将流的所有内容读取到内存中。
  
对于自动完成操作, outlook 在 outlook .exe 进程生存期内以独占方式与此内存中的结构交互。 Outlook 仅在关闭时保存该结构。 有关此过程的详细信息, 请参阅以下部分 "保存自动完成流"。
  
## <a name="saving-the-autocomplete-stream"></a>保存自动完成流

如果自动完成列表已通过以下任一方式发生更改, Outlook 会在关闭时保存自动完成流:
  
- 通过解析名称, 从 "通讯簿" 对话框中选取收件人, 或将邮件发送到列表中尚未列出的收件人, 添加一个新的昵称条目。
    
- 通过将邮件发送到列表中的现有收件人来修改条目。
    
- 用户通过 UI 删除条目。
    
- 与本主题不相关的其他次要方案。
    
保存对自动完成数据的更改涉及将内存中的结构写回到[自动完成流](autocomplete-stream.md)中。 在与 Outlook 2007 交互时, 会将该流保存到 nk2 文件中。 对于 outlook 2010 或 outlook 2013, 自动完成流会写回到邮件帐户的送达存储区的 "收件箱" 的 "关联的内容" 表中。
  
## <a name="recommendations"></a>建议

- 从不部分修改自动完成流。 受支持的交互为 1) 将整个自动完成流读取到内存, 2)。修改内存结构和 3) 将整个流写入邮件帐户的传递存储收件箱的 "关联的内容" 表 (对于 Outlook 2010 或outlook 2013) 或本地 nk2 文件 (outlook 2007)。
    
- 当 Outlook 正在运行时, 请勿与自动完成流进行交互。 如果在您修改流时 Outlook 正在运行, 则它可能会在您的更改关闭时覆盖您所做的更改。
    
- 请勿将类型为 PT_MV_UNICODE 和 PR_MV_STRING8 的属性写入 Microsoft Outlook 2003 将使用的自动完成流中。 只有 outlook 2007、outlook 2010 和 outlook 2013 可以理解这些属性。
    
- 在开发与 Outlook 2007 交互的代码时, 我们建议您在使用标准文件锁定 api (例如, c/c + + 中的**LockFile**和 nk2 文件) 中的其他过程中锁定和写入文件, 然后再**进行修改。** 以 c # 为单位的 FileStream)。 
    
- 仅修改自动完成流的行集中的类型的属性。 有关自动完成流属性和属性类型的详细信息, 请参阅[自动完成流](autocomplete-stream.md)。
    
## <a name="see-also"></a>另请参阅



[自动完成流](autocomplete-stream.md)
  
[MAPI 配置文件](mapi-profiles.md)


[Outlook 2003/2007 NK2 文件格式和开发人员指南](https://portalvhds6gyn3khqwmgzd.blob.core.windows.net/files/NK2/NK2WithBinaryExample.pdf)

