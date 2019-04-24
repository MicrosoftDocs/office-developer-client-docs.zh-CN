---
title: 传输提供程序示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ec6eb6c0-bfe3-4989-9071-89a14c0e7bdd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: def51a752abcb79a35980ed12eb73011c26d2597
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356586"
---
# <a name="transport-provider-sample"></a>传输提供程序示例

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此示例使用文件和目录传输和接收邮件。 它实现并注册一个非常简单的预处理器, 将一行文本追加到每个出站邮件。 此示例说明如何在传输中性封装格式 (TNEF) 和文本之间拆分邮件内容。 它还支持所有配置选项 (属性表、向导和编程配置) 和邮件选项。 它不支持远程传输接口。 
  
您可以从[Outlook 消息处理 API (MAPI) 代码示例](https://go.microsoft.com/fwlink/?LinkId=129740)中下载此示例。
  
|||
|:-----|:-----|
|执行  <br/> |mrxp32  <br/> |
|源代码目录:  <br/> |SampleTransportProvider\MRXP  <br/> |
|语言  <br/> |c  <br/> |
|平台  <br/> |用于编译 windows Vista、windows server 2008、windows XP SP2 和 Windows Server 2003 SP1 的 Visual Studio 2008  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持以下功能:
  
- 新邮件的发送、接收和轮询等基本功能。
    
- 交互式和编程配置。
    
- **IMAPIStatus**接口, 属性设置除外。 有关详细信息, 请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md) interface。 
    
- 线程安全性。
    
- 事件日志记录到文本文件。 文件将自动限制为指定大小。 所有传输会话都使用相同的文件。
    
## <a name="unsupported-features"></a>不支持的功能

此示例不支持对传入邮件进行异步检测。
  
 **安装示例传输提供程序**
  
1. 若要下载示例传输提供程序, 请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到保存 Outlook MAPI 示例的文件夹。 右键单击 " **OutlookMAPISamples\<\>号码**" zip 文件夹, 然后单击 "**全部提取**"。
    
3. 单击 "**浏览**", 选择要保存示例的位置, 然后单击 "**提取**"。
    
4. 运行 Visual Studio 2008。
    
5. 在 Visual Studio 2008 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。
    
6. 浏览到保存示例的位置, 单击 " **mrxp32**", 然后单击 "**打开**"。
    
7. 在 "**生成**" 菜单上, 单击 "**配置管理器**"。
    
8. 在 "**配置管理器**" 对话框中, 转到 " **mrxp32** " 行, 然后在 "**配置**" 列中选择 "**发布**", 然后单击 "**关闭**"。
    
9. 在"构建"菜单上，单击"构建解决方案"。
    
10. 在 "**将文件另存为**" 对话框中, 单击 "**保存**"。
    
11. 在保存该示例的文件夹中, 右键单击该安装批处理文件, 然后单击 "**以管理员身份运行**"。
    
12. 在“用户帐户控制”**** 对话框中，单击“继续”****。
    
    > [!NOTE]
    > **.bat**将 .dll 复制到默认的 Microsoft Office 安装文件夹中, C:\Program Files\Microsoft Office\Office12\. 如果您已将 Office 产品安装在其他位置, 请右键单击 " **install** ", 然后单击 "**编辑**"。 文件将在记事本中打开。 将默认安装路径替换为计算机上使用的安装路径。 
  
 **在 Outlook 中设置传输提供程序**
  
1. 在 Outlook 的 "**工具**" 菜单上, 单击 "**帐户设置**"。
    
2. 在 "**帐户设置**" 对话框中的 "**电子邮件**" 选项卡上, 单击 "**新建**"。
    
3. 在 "**选择电子邮件服务**" 下单击 "**其他**", 选择**MRXP 示例传输**, 然后单击 "**下一步**"。
    
4. 在 " **MRXP 传输配置**" 对话框中, 键入**用户显示名称**。
    
5. 在 **"收件箱 (UNC 共享) 的路径**" 下, 输入文件夹路径。 这也可以是本地文件夹的路径。 
    
    > [!IMPORTANT]
    > 此路径必须存在。 
  
6. 单击“**确定**”。
    
7. 在 "**添加电子邮件帐户**" 对话框中, 单击 **"确定"**。 单击 "**完成**", 然后单击 "**关闭**"。
    
8. 若要开始使用 MRXP 帐户, 请退出并重新启动 Outlook。
    
 **使用传输提供程序示例在 Outlook 中发送邮件**
  
1. 在 "**文件**" 菜单上, 单击 "**新建**", 然后单击 "**邮件**"。
    
2. 在 "**收件人**" 框中, 键入使用 " **[MRXP\<\>: ADDRESS]**" 格式的收件人的名称。 该地址是收件人的收件箱的 UNC 共享或本地文件夹路径。
    
    > [!NOTE]
    > 如果地址中有冒号或反斜杠, 则必须在每个冒号或反斜杠前插入一个反斜杠。 例如, 若要将邮件发送到 [MRXP: \Mail\myDir], 则必须键入`[MRXP:C\:\\Mail\\myDir]`。 
  
    > [!IMPORTANT]
    > 收件人地址必须存在。 
  
3. 单击 "**帐户**", 然后单击 " **MRXP 示例传输**"。
    
4. 键入您的消息并单击 "**发送**"。 将使用 MRXP 传输提供程序发送邮件。
    
 **使用传输提供程序示例在 Outlook 中接收邮件**
  
1. 在 "**文件**" 菜单上, 单击 "**新建**", 然后单击 "**邮件**"。
    
2. 键入您的消息。
    
3. 单击 " **Microsoft Office 按钮**", 单击 "**另存为**", 然后单击 "**另存为**", 将文件保存到在安装过程中指定的 "收件箱" 文件夹中。 
    
4. 在 "**另存为**" 对话框中, 浏览到您设置为 "收件箱" 的 UNC 共享或本地文件夹。 
    
5. 在 "**保存类型**" 下拉下拉箭头中, 单击 " **Outlook 邮件格式**"。
    
6. 键入文件的名称, 然后单击 "**保存**"。
    
7. 将文件保存到共享文件夹。 MRXP 传输提供程序将邮件传递到 Outlook 中的 "收件箱"。
    

