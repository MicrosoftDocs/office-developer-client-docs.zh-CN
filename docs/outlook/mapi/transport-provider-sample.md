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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401403"
---
# <a name="transport-provider-sample"></a>传输提供程序示例

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此示例使用文件和目录传输和接收消息。 它实现并注册的非常简单预处理程序将一行文本追加到每个出站邮件。 该示例演示如何拆分传输中性封装格式 (TNEF) 和文本之间的消息内容。 它还支持所有配置选项 （属性表、 向导和编程配置） 和消息选项。 它不支持远程传输接口。 
  
您可以从[Outlook 消息处理 API (MAPI) 代码示例](https://go.microsoft.com/fwlink/?LinkId=129740)下载此示例。
  
|||
|:-----|:-----|
|可执行文件：  <br/> |mrxp32.dll  <br/> |
|源代码目录：  <br/> |SampleTransportProvider\MRXP  <br/> |
|语言：  <br/> |C++  <br/> |
|平台：  <br/> |对于 Windows Vista、 Windows Server 2008、 Windows XP SP2 和 Windows Server 2003 SP1 编译 visual Studio 2008  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持以下功能：
  
- 如发送、 接收和轮询新邮件的基本功能。
    
- 交互式和编程方式配置。
    
- 除属性设置为**IMAPIStatus**接口。 有关详细信息，请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。 
    
- 线程安全性。
    
- 事件日志记录到文本文件。 文件是自动为指定大小限制。 所有传输会话都使用相同的文件。
    
## <a name="unsupported-features"></a>不支持的功能

此示例不支持异步检测的传入消息。
  
 **安装示例传输提供程序**
  
1. 若要下载示例传输提供程序，请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到的 Outlook MAPI 示例的保存位置的文件夹。 右键单击**OutlookMAPISamples-\<版本号\>** zip 文件夹，然后单击**全部提取**。
    
3. 单击**浏览**，选择要用于保存该示例的位置，然后单击**提取**。
    
4. 运行 Visual Studio 2008。
    
5. 在 Visual Studio 2008 中，单击**文件**，选择**打开**，然后单击**项目/解决方案**。
    
6. 浏览到保存该示例的位置，单击**mrxp32.vcproj**，，然后单击**打开**。
    
7. 在**生成**菜单上，单击**配置管理器**。
    
8. **配置管理器**对话框中，转到**mrxp32**行中，和**配置**列中选择**版本**中，，然后单击**关闭**。
    
9. 在"构建"菜单上，单击"构建解决方案"。
    
10. 在**将文件另存为**对话框中，单击**保存**。
    
11. 在本示例保存的文件夹，右键单击安装批处理文件，然后单击**以管理员身份运行**。
    
12. 在**用户帐户控制**对话框中，单击**继续**。
    
    > [!NOTE]
    > **install.bat**复制.dll 默认 Microsoft Office 安装文件夹，C:\Program Files\Microsoft Office\Office12\. 如果您已在其他位置安装 Office 产品，右键单击**install.bat** ，然后单击**编辑**。 在记事本中打开该文件。 默认安装路径替换为您的计算机上使用的安装路径。 
  
 **若要设置在 Outlook 中传输提供程序**
  
1. 在 Outlook**工具**菜单上，单击**帐户设置**。
    
2. 在**帐户设置**对话框的**电子邮件**选项卡中，单击**新建**。
    
3. 在**选择电子邮件服务**下单击**其他**，选择**MRXP 示例传输**，，然后单击**下一步**。
    
4. 在**MRXP 传输配置**对话框中键入**用户的显示名称**。
    
5. 在**收件箱 （UNC 共享） 的路径**下输入的文件夹路径。 也可以是到本地文件夹的路径。 
    
    > [!IMPORTANT]
    > 必须存在此路径。 
  
6. 单击“确定”****。
    
7. 在**添加电子邮件帐户**对话框中单击**确定**。 单击**完成**，然后单击**关闭**。
    
8. 要开始使用 MRXP 帐户，请退出并重新启动 Outlook。
    
 **使用传输提供程序示例在 Outlook 中发送消息**
  
1. 在**文件**菜单中，单击**新建**，然后单击**邮件**。
    
2. 在**到**框中键入的收件人使用的格式名称 **[MRXP:\<地址\>]**。 该地址是 UNC 共享或到收件人的收件箱的本地文件夹路径。
    
    > [!NOTE]
    > 如果有冒号或地址中的反斜杠，必须在每个冒号或反斜杠之前插入反斜杠。 例如，要发送到的邮件 [MRXP:C:\Mail\myDir] 必须键入`[MRXP:C\:\\Mail\\myDir]`。 
  
    > [!IMPORTANT]
    > 收件人地址必须存在。 
  
3. 单击**帐户**，然后单击**MRXP 示例传输**。
    
4. 键入消息，然后单击**发送**。 使用 MRXP 传输提供程序发送邮件。
    
 **要用于在 Outlook 中收到一条消息传输提供程序示例**
  
1. 在**文件**菜单中，单击**新建**，然后单击**邮件**。
    
2. 键入您的消息。
    
3. 单击**Microsoft Office 按钮**，单击**另存为**，然后单击**另存为**文件保存到您在安装过程中指定的收件箱文件夹。 
    
4. 在**另存为**对话框中，浏览到 UNC 共享或设置为您的收件箱的本地文件夹。 
    
5. 在**保存类型**下拉列表，单击**Outlook 邮件格式**。
    
6. 键入文件的名称，然后单击**保存**。
    
7. 将文件保存到共享文件夹。 MRXP 传输提供程序将邮件传递到 Outlook 中的收件箱。
    

