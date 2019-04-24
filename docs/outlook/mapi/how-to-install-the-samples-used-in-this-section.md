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
  
若要安装 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目以查看并运行 "[使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)" 部分中的主题所引用的示例代码, 请按照以下步骤操作。 

若要下载并安装 "使用 MAPI 创建 Outlook 项目" 部分中使用的示例, 请执行以下步骤。

### <a name="to-download-and-install-the-mfcmapi-application-and-open-createoutlookitemsaddin-project"></a>下载并安装 MFCMAPI 应用程序并打开 CreateOutlookItemsAddin 项目

1. 将当前版本的[MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154)可执行文件下载到系统上的文件夹中。 
    
2. 提取 MFCMapi 中的 MFCMapi 文件。 __ 将 .zip 文件夹压缩到硬盘上的空文件夹。
    
3. 下载当前版本的[CreateOutlookItemsAddin](https://go.microsoft.com/fwlink/?LinkID=127828)项目。 
    
4. 将 CreateOutlookItemsAddin 文件中的所有文件提取到您在步骤2中提取 MFCMapi 文件的文件夹中。
    
5. 将步骤2中使用的文件夹中的 MFCMapi 复制到 CreateOutlookItemsAddin 项目的生成目录 (\CreateOutlookItemsAddin\Debug)。
    
6. 在 Visual Studio 中打开 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj) 以检查源代码。 请参阅 "[使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)" 部分中的主题, 以确定要打开的源文件。 
    
## <a name="run-mfcmapi-and-the-createoutlookitemsaddin-project"></a>运行 MFCMAPI 和 CreateOutlookItemsAddin 项目

以下步骤假定您已下载并安装了当前版本的 MFCMAPI 可执行文件和 CreateOutlookItemsAddin 项目, 如前面的过程中所述。 这些步骤将指导您使用 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目来创建 Outlook 项目的**Addins**菜单项。 
  
> [!NOTE]
> 您在步骤8中选择的文件夹和在步骤9中选择的命令取决于 "[使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)" 部分中的某个主题中讨论的项目类型。 

### <a name="to-run-the-mfcmapi-application-and-addins-menu-commands"></a>运行 MFCMAPI 应用程序和 Addins 菜单命令

1. 在按照安装说明执行操作时创建的 CreateOutlookItemsAddin\Debug 文件夹中启动 Mfcmapi。
    
2. 单击 **"确定"** 以消除 MFCMAPI 初始屏幕。 
    
3. 在 "**会话**" 菜单上, 单击 "**登录并显示存储表**"。
    
4. 在 "**选择配置文件**" 对话框中, 选择正确的配置文件, 然后单击 **"确定"**。 
    
5. 双击 "存储表列表" 视图中的 "**邮箱- _[用户名]_ ** "。 
    
6. 在文件夹树视图中, 展开根节点。 根据所选配置文件类型的不同, 为根节点显示的名称会有所不同。 通常, 此节点显示为**根邮箱**。
    
7. 在文件夹树视图中, 展开包含信息存储的节点。 为此节点显示的名称根据所选配置文件类型的不同而不同。 通常, 此节点显示为**IPM_SUBTREE**或**Top 信息存储区**。
    
8. 双击要创建的项目类型所对应的文件夹。 例如, 若要创建约会, 请单击 "**约会**" 文件夹。 
    
9. 在 " **Addins** " 菜单上, 单击要创建的项目的相应命令。 
    
## <a name="download-and-view-code-from-the-mfcmapi-application"></a>从 MFCMAPI 应用程序下载和查看代码

一些主题指的是来自 MFCMAPI 应用程序本身的源代码。 下面的步骤介绍了如何下载 MFCMAPI 源代码并在 Visual Studio 中查看该源代码。 

### <a name="to-download-and-view-the-mfcmapi-application-source-code"></a>下载和查看 MFCMAPI 应用程序源代码

1. 将当前版本的[MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154)应用程序的源代码下载到系统上的文件夹中。 
    
2. 将 MFCMAPI 中的文件提取__ 到硬盘驱动器上的空文件夹中。
    
3. 在 Visual Studio 中打开 MFCMapi 项目 (\_文件夹_\ MFCMapi vcproj) 以检查源代码。
    
## <a name="see-also"></a>另请参阅

- [创建简单邮件项](how-to-create-a-simple-mail-item.md)
- [创建简单的重复性任务项](how-to-create-a-simple-recurrent-task-item.md)
- [创建复杂的定期约会项目](how-to-create-a-complex-recurrent-appointment-item.md)
- [读取和分析定期模式](how-to-read-and-parse-a-recurrence-pattern.md)

