---
title: 安装本部分中使用的示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 810f54bf-5b78-46b8-a617-4f61ff816400
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 288ece7a26fb89fa240339da681f163909124823
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345547"
---
# <a name="install-the-samples-used-in-this-section"></a>安装本部分中使用的示例

**适用于**：Outlook 2013 | Outlook 2016 
  
若要安装 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目以查看并运行使用[MAPI](creating-outlook-items-by-using-mapi.md)创建 Outlook 项部分中的主题引用的示例代码，请按照以下步骤操作。 

若要下载并安装"使用 MAPI 创建项目Outlook中使用的示例，请按照以下步骤操作。

### <a name="to-download-and-install-the-mfcmapi-application-and-open-createoutlookitemsaddin-project"></a>下载并安装 MFCMAPI 应用程序并打开 CreateOutlookItemsAddin 项目

1. 将当前版本的 [MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) 可执行文件下载到系统上的文件夹。 
    
2. 在MFCMapi.exe中提取文件MFCMapi.exe。 _version_.zip 硬盘上的空文件夹。
    
3. 下载 [CreateOutlookItemsAddin](https://go.microsoft.com/fwlink/?LinkID=127828) 项目的当前版本。 
    
4. 将文件文件CreateOutlookItemsAddin.zip文件解压缩到步骤 2 中解压缩MFCMapi.exe文件的文件夹。
    
5. 将MFCMapi.exe 2 中使用的文件夹复制到 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\Debug) 的生成目录。
    
6. 打开 Visual Studio 中的 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj) 以检查源代码。 请参阅使用[MAPI](creating-outlook-items-by-using-mapi.md)创建Outlook项"部分的主题，以确定要打开的源文件。 
    
## <a name="run-mfcmapi-and-the-createoutlookitemsaddin-project"></a>运行 MFCMAPI 和 CreateOutlookItemsAddin 项目

以下步骤假定你已下载并安装当前版本的 MFCMAPI 可执行文件和 CreateOutlookItemsAddin 项目，如上一过程中所述。 这些步骤将指导您找到 **Addins** 菜单项，这些菜单项使您能够使用 MFCMAPI Outlook CreateOutlookItemsAddin 项目创建项目。 
  
> [!NOTE]
> 在步骤 8 中选择的文件夹以及步骤 9 中选择的命令取决于"使用 MAPI 创建 Outlook 项目["部分的主题之](creating-outlook-items-by-using-mapi.md)一中讨论的项目类型。 

### <a name="to-run-the-mfcmapi-application-and-addins-menu-commands"></a>运行 MFCMAPI 应用程序和 Addins 菜单命令

1. Start Mfcmapi.exe in the CreateOutlookItemsAddin\Debug folder that is created when you follow the installation instructions.
    
2. 单击 **"确定** "关闭 MFCMAPI 初始屏幕。 
    
3. 在"**会话"** 菜单上，单击 **"登录并显示存储表"。**
    
4. 在"**选择配置文件**"对话框中，选择正确的配置文件，然后单击"确定 **"。** 
    
5. 在存储表 **列表 _视图中双击_"邮箱 - [** 用户名]"。 
    
6. 在文件夹树视图中，展开根节点。 为根节点显示的名称因所选配置文件的类型而异。 通常，此节点显示为"根 **- 邮箱"。**
    
7. 在文件夹树视图中，展开包含信息存储的节点。 为此节点显示的名称因所选配置文件的类型而异。 通常，此节点显示为 **"IPM_SUBTREE** 存储 **"或"顶部"。**
    
8. 双击要创建的项目类型的文件夹。 例如，若要创建约会，请单击 **"约会"** 文件夹。 
    
9. 在 **"加载项"菜单** 上，单击要创建项的适当命令。 
    
## <a name="download-and-view-code-from-the-mfcmapi-application"></a>从 MFCMAPI 应用程序下载和查看代码

一些主题引用 MFCMAPI 应用程序本身的源代码。 以下步骤介绍如何下载 MFCMAPI 源代码，以及如何在 Visual Studio。 

### <a name="to-download-and-view-the-mfcmapi-application-source-code"></a>下载和查看 MFCMAPI 应用程序源代码

1. 将当前版本的 [MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) 应用程序的源代码下载到系统上的文件夹。 
    
2. 将 MFCMAPI 更改 _集_.zip文件解压缩到硬盘驱动器上的空文件夹。
    
3. 打开 MFCMapi 项目 (\ _foldername_\ MFCMapi.vcproj) 中Visual Studio检查源代码。
    
## <a name="see-also"></a>另请参阅

- [创建简单邮件项目](how-to-create-a-simple-mail-item.md)
- [创建简单重复性任务项](how-to-create-a-simple-recurrent-task-item.md)
- [创建复杂定期约会项目](how-to-create-a-complex-recurrent-appointment-item.md)
- [读取和分析定期模式](how-to-read-and-parse-a-recurrence-pattern.md)

