---
title: 安装使用本节中的示例
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 810f54bf-5b78-46b8-a617-4f61ff816400
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 288ece7a26fb89fa240339da681f163909124823
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397056"
---
# <a name="install-the-samples-used-in-this-section"></a>安装使用本节中的示例

**适用于**：Outlook 2013 | Outlook 2016 
  
若要安装的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目查看和运行代码示例[通过使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)部分中的主题引用，请按照下列步骤。 

若要下载并安装在"使用 MAPI 创建 Outlook 项目"中使用的示例部分中，请按照下列步骤。

### <a name="to-download-and-install-the-mfcmapi-application-and-open-createoutlookitemsaddin-project"></a>若要下载和安装 MFCMAPI 应用程序并打开 CreateOutlookItemsAddin 项目

1. 下载到您的系统上的文件夹的当前版本的可执行[MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) 。 
    
2. 提取中 MFCMapi.exe MFCMapi.exe 文件。 在您的硬盘上的空文件夹_版本_.zip。
    
3. 下载[CreateOutlookItemsAddin](https://go.microsoft.com/fwlink/?LinkID=127828)项目的当前版本。 
    
4. 提取 CreateOutlookItemsAddin.zip 文件提取到在步骤 2 中的 MFCMapi.exe 文件的文件夹中的所有文件。
    
5. 从文件夹用于在步骤 2 中生成目录 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\Debug) 复制 MFCMapi.exe。
    
6. 要检查的源代码的 Visual Studio 中打开 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj)。 从[通过使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)部分，以确定哪些源文件以打开参考主题。 
    
## <a name="run-mfcmapi-and-the-createoutlookitemsaddin-project"></a>运行 MFCMAPI 和 CreateOutlookItemsAddin 项目

下面的步骤假定您已下载并安装 MFCMAPI 可执行文件和 CreateOutlookItemsAddin 项目前面过程中所述的当前版本。 以下步骤将指导您使您能够创建使用 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目的 Outlook 项目的**加载项**菜单项。 
  
> [!NOTE]
> 步骤 8 和步骤 9 中选择的命令中选择的文件夹取决于从[通过使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)部分的主题之一中讨论的项类型。 

### <a name="to-run-the-mfcmapi-application-and-addins-menu-commands"></a>若要运行的 MFCMAPI 应用程序和加载项菜单命令

1. 启动 Mfcmapi.exe 按照安装说明时，将创建的 CreateOutlookItemsAddin\Debug 文件夹中。
    
2. 单击**确定**以关闭 MFCMAPI 初始屏幕。 
    
3. 在**会话**菜单中，单击**登录名和显示存储表**。
    
4. 在**选择配置文件**对话框中，选择正确的配置文件，然后单击**确定**。 
    
5. 双击存储表的列表视图中的**邮箱- _[用户名]_ ** 。 
    
6. 在文件夹树视图中，展开根节点。 显示的根节点取决于所选的配置文件的类型的名称。 此节点通常显示为**根-邮箱**。
    
7. 在文件夹树视图中，展开包含的信息存储节点。 显示为此节点取决于所选的配置文件的类型的名称。 通常为**IPM_SUBTREE**或**信息存储的顶部**显示此节点。
    
8. 双击要创建的项目类型的文件夹。 例如，若要创建约会，请单击**约会**文件夹。 
    
9. 在**外接程序**菜单中，单击项目创建适当的命令。 
    
## <a name="download-and-view-code-from-the-mfcmapi-application"></a>下载并查看 MFCMAPI 应用程序的代码

某些主题引用 MFCMAPI 应用程序本身的源代码。 以下步骤介绍如何下载 MFCMAPI 源代码和 Visual Studio 中进行查看。 

### <a name="to-download-and-view-the-mfcmapi-application-source-code"></a>下载并查看 MFCMAPI 应用程序的源代码

1. 下载到您的系统上的文件夹的[MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154)应用程序的当前版本的源代码。 
    
2. 在您的硬盘上的空文件夹 MFCMAPI-_变更集_.zip 文件提取。
    
3. 打开 MFCMapi 项目 (\_文件夹名称_\ MFCMapi.vcproj) 在 Visual Studio 中检查的源代码。
    
## <a name="see-also"></a>另请参阅

- [创建简单邮件项](how-to-create-a-simple-mail-item.md)
- [创建简单重复任务项](how-to-create-a-simple-recurrent-task-item.md)
- [创建复杂重复约会项](how-to-create-a-complex-recurrent-appointment-item.md)
- [读取和分析定期模式](how-to-read-and-parse-a-recurrence-pattern.md)

