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
  
此示例使用文件和目录传输和接收消息。 它实现并注册一个非常简单的预处理器，它将一行文本附加到每个出站邮件。 该示例说明如何在传输中性封装格式与 TNEF 格式和文本 (拆分) 内容。 它还支持所有配置选项 (、向导以及编程配置) 和消息选项。 它不支持远程传输接口。 
  
可以从 MAPI 代码示例[Outlook消息 API (下载) 示例](https://go.microsoft.com/fwlink/?LinkId=129740)。
  
|||
|:-----|:-----|
|可执行文件：  <br/> |mrxp32.dll  <br/> |
|源代码目录：  <br/> |SampleTransportProvider\MRXP  <br/> |
|语言：  <br/> |C++  <br/> |
|平台：  <br/> |Visual Studio 2008 年Windows Vista、Windows Server 2008、Windows XP SP2 和 Windows Server 2003 SP1 编译  <br/> |
   
## <a name="supported-features"></a>支持的功能

此示例支持以下功能：
  
- 基本功能，如发送、接收和轮询新邮件。
    
- 交互式和编程配置。
    
- **IMAPIStatus** 接口，属性设置除外。 有关详细信息，请参阅 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md) 接口。 
    
- 线程安全。
    
- 事件记录到文本文件。 文件自动限制为指定大小。 所有传输会话都使用相同的文件。
    
## <a name="unsupported-features"></a>不受支持的功能

此示例不支持对传入邮件进行异步检测。
  
 **安装示例传输提供程序**
  
1. 若要下载示例传输提供程序，请参阅下载Outlook [MAPI 示例](downloading-the-outlook-mapi-samples.md)。
    
2. 找到保存 MAPI 示例Outlook文件夹。 右键单击 **"OutlookMAPISamples- \< 版本号 \>** zip"文件夹，然后单击"**全部提取"。**
    
3. 单击 **"** 浏览"，选择要保存示例的位置，然后单击"提取 **"。**
    
4. 运行 Visual Studio 2008。
    
5. 在 Visual Studio 2008 中，单击"文件"，选择"打开 **"，然后单击"Project/解决方案"。**
    
6. 浏览到保存示例的位置，单击 **mrxp32.vcproj，** 然后单击"打开 **"。**
    
7. 在"生成 **"菜单** 上，单击 **"配置管理器"。**
    
8. 在 **"配置管理器**"对话框中，转到 **"mrxp32"** 行，然后在"配置"列中选择"发布"，然后单击"关闭 **"。**
    
9. 在"构建"菜单上，单击"构建解决方案"。
    
10. 在"**将文件另存为**"对话框中，单击"保存 **"。**
    
11. 在保存示例的文件夹中，右键单击安装批处理文件，然后单击"以 **管理员角色运行"。**
    
12. 在“用户帐户控制”对话框中，单击“继续”。
    
    > [!NOTE]
    > **install.bat** 将.dll复制到默认Microsoft Office文件夹 C：\Program Files\Microsoft Office\Office12\. If you have installed Office products in a different location， right-click **install.bat** and click **Edit**. 文件将在记事本。 将默认安装路径替换为计算机上使用的安装路径。 
  
 **在传输服务中设置传输Outlook**
  
1. 在"**工具"** 菜单上的Outlook，单击"**帐户设置"。**
    
2. 在"**帐户设置** 对话框中的"电子邮件 **"选项卡上**，单击"新建 **"。**
    
3. 在"**选择电子邮件服务**"下，单击"**其他"，** 选择 **"MRXP 示例传输**"，然后单击"下一 **步"。**
    
4. 在 **"MRXP 传输配置**"对话框中，键入 **"用户显示名称"。**
    
5. 在 **"收件箱路径 (UNC 共享)** 输入文件夹路径。 这还可以是本地文件夹的路径。 
    
    > [!IMPORTANT]
    > 此路径必须存在。 
  
6. 单击“**确定**”。
    
7. 在"**添加电子邮件帐户"对话框中**，单击"确定 **"。** 单击 **"完成**"，然后单击"关闭 **"。**
    
8. 若要开始使用 MRXP 帐户，请退出并重新启动Outlook。
    
 **使用传输提供程序示例在传输中Outlook**
  
1. 在"**文件"** 菜单上，单击 **"新建**"，然后单击"**邮件"。**
    
2. 在 **"收件人** "框中，使用 **格式 [MRXP： ADDRESS ] 键入 \< \> 收件人的姓名**。 地址是收件人收件箱的 UNC 共享或本地文件夹路径。
    
    > [!NOTE]
    > 如果地址中存在冒号或反杠，则必须在每个冒号或反杠之前插入反杠。 例如，若要向 [MRXP：C：\Mail\myDir] 发送邮件，必须键入  `[MRXP:C\:\\Mail\\myDir]` 。 
  
    > [!IMPORTANT]
    > 收件人地址必须存在。 
  
3. 单击 **帐户** ，然后单击 **MRXP 示例传输**。
    
4. 键入邮件，然后单击"发送 **"。** 邮件使用 MRXP 传输提供程序发送。
    
 **使用传输提供程序示例在邮件中接收Outlook**
  
1. 在"**文件"** 菜单上，单击 **"新建**"，然后单击"**邮件"。**
    
2. 键入邮件。
    
3. 单击 **"Microsoft Office按钮**"，单击"另存为"，然后单击"另存为"将文件保存到在设置期间指定的收件箱文件夹中。 
    
4. 在 **"另存为** "对话框中，浏览到您设置为收件箱的 UNC 共享或本地文件夹。 
    
5. 在"**另存为类型"** 下拉列表中，单击 **"Outlook格式"。**
    
6. 键入文件的名称，然后单击"保存 **"。**
    
7. 文件保存到共享文件夹。 MRXP 传输提供程序将邮件发送到收件箱Outlook。
    

