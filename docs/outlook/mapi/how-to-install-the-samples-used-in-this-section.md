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
# <a name="install-the-samples-used-in-this-section"></a><span data-ttu-id="27d02-103">安装本部分中使用的示例</span><span class="sxs-lookup"><span data-stu-id="27d02-103">Install the samples used in this section</span></span>

<span data-ttu-id="27d02-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27d02-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27d02-105">若要安装 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目以查看并运行使用[MAPI](creating-outlook-items-by-using-mapi.md)创建 Outlook 项部分中的主题引用的示例代码，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="27d02-105">To install the MFCMAPI application and CreateOutlookItemsAddin project to view and run the sample code referenced by the topics in the [Creating Outlook Items by Using MAPI](creating-outlook-items-by-using-mapi.md) section, follow these steps.</span></span> 

<span data-ttu-id="27d02-106">若要下载并安装"使用 MAPI 创建项目Outlook中使用的示例，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="27d02-106">To download and install the examples used in the "Using MAPI to create Outlook items" section, follow these steps.</span></span>

### <a name="to-download-and-install-the-mfcmapi-application-and-open-createoutlookitemsaddin-project"></a><span data-ttu-id="27d02-107">下载并安装 MFCMAPI 应用程序并打开 CreateOutlookItemsAddin 项目</span><span class="sxs-lookup"><span data-stu-id="27d02-107">To download and install the MFCMAPI application and open CreateOutlookItemsAddin project</span></span>

1. <span data-ttu-id="27d02-108">将当前版本的 [MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) 可执行文件下载到系统上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-108">Download the current version of the [MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) executable to a folder on your system.</span></span> 
    
2. <span data-ttu-id="27d02-109">在MFCMapi.exe中提取文件MFCMapi.exe。</span><span class="sxs-lookup"><span data-stu-id="27d02-109">Extract the MFCMapi.exe file in MFCMapi.exe.</span></span> <span data-ttu-id="27d02-110">_version_.zip 硬盘上的空文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-110">_version_.zip to an empty folder on your hard drive.</span></span>
    
3. <span data-ttu-id="27d02-111">下载 [CreateOutlookItemsAddin](https://go.microsoft.com/fwlink/?LinkID=127828) 项目的当前版本。</span><span class="sxs-lookup"><span data-stu-id="27d02-111">Download the current version of the [CreateOutlookItemsAddin](https://go.microsoft.com/fwlink/?LinkID=127828) project.</span></span> 
    
4. <span data-ttu-id="27d02-112">将文件文件CreateOutlookItemsAddin.zip文件解压缩到步骤 2 中解压缩MFCMapi.exe文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-112">Extract all the files in the CreateOutlookItemsAddin.zip file to the folder where you extracted the MFCMapi.exe file in Step 2.</span></span>
    
5. <span data-ttu-id="27d02-113">将MFCMapi.exe 2 中使用的文件夹复制到 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\Debug) 的生成目录。</span><span class="sxs-lookup"><span data-stu-id="27d02-113">Copy MFCMapi.exe from the folder used in Step 2 to the build directory for the CreateOutlookItemsAddin project (\CreateOutlookItemsAddin\Debug).</span></span>
    
6. <span data-ttu-id="27d02-114">打开 Visual Studio 中的 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj) 以检查源代码。</span><span class="sxs-lookup"><span data-stu-id="27d02-114">Open the CreateOutlookItemsAddin project (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj) in Visual Studio to examine the source code.</span></span> <span data-ttu-id="27d02-115">请参阅使用[MAPI](creating-outlook-items-by-using-mapi.md)创建Outlook项"部分的主题，以确定要打开的源文件。</span><span class="sxs-lookup"><span data-stu-id="27d02-115">Refer to the topics from the [Creating Outlook Items by Using MAPI](creating-outlook-items-by-using-mapi.md) section to determine which source files to open.</span></span> 
    
## <a name="run-mfcmapi-and-the-createoutlookitemsaddin-project"></a><span data-ttu-id="27d02-116">运行 MFCMAPI 和 CreateOutlookItemsAddin 项目</span><span class="sxs-lookup"><span data-stu-id="27d02-116">Run MFCMAPI and the CreateOutlookItemsAddin project</span></span>

<span data-ttu-id="27d02-117">以下步骤假定你已下载并安装当前版本的 MFCMAPI 可执行文件和 CreateOutlookItemsAddin 项目，如上一过程中所述。</span><span class="sxs-lookup"><span data-stu-id="27d02-117">The following steps assume that you have downloaded and installed the current version of the MFCMAPI executable and the CreateOutlookItemsAddin project as described in the preceding procedure.</span></span> <span data-ttu-id="27d02-118">这些步骤将指导您找到 **Addins** 菜单项，这些菜单项使您能够使用 MFCMAPI Outlook CreateOutlookItemsAddin 项目创建项目。</span><span class="sxs-lookup"><span data-stu-id="27d02-118">These steps will guide you to the **Addins** menu items that enable you to create Outlook items using the MFCMAPI application and the CreateOutlookItemsAddin project.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="27d02-119">在步骤 8 中选择的文件夹以及步骤 9 中选择的命令取决于"使用 MAPI 创建 Outlook 项目["部分的主题之](creating-outlook-items-by-using-mapi.md)一中讨论的项目类型。</span><span class="sxs-lookup"><span data-stu-id="27d02-119">The folder you select in step 8, and the command you select in step 9, depends on the item type discussed in one of the topics from the [Creating Outlook Items by Using MAPI](creating-outlook-items-by-using-mapi.md) section.</span></span> 

### <a name="to-run-the-mfcmapi-application-and-addins-menu-commands"></a><span data-ttu-id="27d02-120">运行 MFCMAPI 应用程序和 Addins 菜单命令</span><span class="sxs-lookup"><span data-stu-id="27d02-120">To run the MFCMAPI application and Addins menu commands</span></span>

1. <span data-ttu-id="27d02-121">Start Mfcmapi.exe in the CreateOutlookItemsAddin\Debug folder that is created when you follow the installation instructions.</span><span class="sxs-lookup"><span data-stu-id="27d02-121">Start Mfcmapi.exe in the CreateOutlookItemsAddin\Debug folder that is created when you follow the installation instructions.</span></span>
    
2. <span data-ttu-id="27d02-122">单击 **"确定** "关闭 MFCMAPI 初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="27d02-122">Click **OK** to dismiss the MFCMAPI splash screen.</span></span> 
    
3. <span data-ttu-id="27d02-123">在"**会话"** 菜单上，单击 **"登录并显示存储表"。**</span><span class="sxs-lookup"><span data-stu-id="27d02-123">On the **Session** menu, click **Logon and Display Store Table**.</span></span>
    
4. <span data-ttu-id="27d02-124">在"**选择配置文件**"对话框中，选择正确的配置文件，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="27d02-124">In the **Choose Profile** dialog box, select the correct profile, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="27d02-125">在存储表 **列表 _视图中双击_"邮箱 - [** 用户名]"。</span><span class="sxs-lookup"><span data-stu-id="27d02-125">Double-click **Mailbox -  _[User Name]_** in the store table list view.</span></span> 
    
6. <span data-ttu-id="27d02-126">在文件夹树视图中，展开根节点。</span><span class="sxs-lookup"><span data-stu-id="27d02-126">In the folder tree view, expand the root node.</span></span> <span data-ttu-id="27d02-127">为根节点显示的名称因所选配置文件的类型而异。</span><span class="sxs-lookup"><span data-stu-id="27d02-127">The name displayed for the root node varies depending on the type of profile selected.</span></span> <span data-ttu-id="27d02-128">通常，此节点显示为"根 **- 邮箱"。**</span><span class="sxs-lookup"><span data-stu-id="27d02-128">Typically this node is displayed as **Root - Mailbox**.</span></span>
    
7. <span data-ttu-id="27d02-129">在文件夹树视图中，展开包含信息存储的节点。</span><span class="sxs-lookup"><span data-stu-id="27d02-129">In the folder tree view, expand the node that contains the information store.</span></span> <span data-ttu-id="27d02-130">为此节点显示的名称因所选配置文件的类型而异。</span><span class="sxs-lookup"><span data-stu-id="27d02-130">The name displayed for this node varies depending on the type of profile selected.</span></span> <span data-ttu-id="27d02-131">通常，此节点显示为 **"IPM_SUBTREE** 存储 **"或"顶部"。**</span><span class="sxs-lookup"><span data-stu-id="27d02-131">Typically this node is displayed as **IPM_SUBTREE** or **Top of Information Store**.</span></span>
    
8. <span data-ttu-id="27d02-132">双击要创建的项目类型的文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-132">Double-click the folder for the item type to create.</span></span> <span data-ttu-id="27d02-133">例如，若要创建约会，请单击 **"约会"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-133">For example, to create an appointment, click the **Appointments** folder.</span></span> 
    
9. <span data-ttu-id="27d02-134">在 **"加载项"菜单** 上，单击要创建项的适当命令。</span><span class="sxs-lookup"><span data-stu-id="27d02-134">On the **Addins** menu, click the appropriate command for the item to create.</span></span> 
    
## <a name="download-and-view-code-from-the-mfcmapi-application"></a><span data-ttu-id="27d02-135">从 MFCMAPI 应用程序下载和查看代码</span><span class="sxs-lookup"><span data-stu-id="27d02-135">Download and view code from the MFCMAPI application</span></span>

<span data-ttu-id="27d02-136">一些主题引用 MFCMAPI 应用程序本身的源代码。</span><span class="sxs-lookup"><span data-stu-id="27d02-136">Some topics refer to source code from the MFCMAPI application itself.</span></span> <span data-ttu-id="27d02-137">以下步骤介绍如何下载 MFCMAPI 源代码，以及如何在 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="27d02-137">The following steps describe how to download the MFCMAPI source code and view it in Visual Studio.</span></span> 

### <a name="to-download-and-view-the-mfcmapi-application-source-code"></a><span data-ttu-id="27d02-138">下载和查看 MFCMAPI 应用程序源代码</span><span class="sxs-lookup"><span data-stu-id="27d02-138">To download and view the MFCMAPI application source code</span></span>

1. <span data-ttu-id="27d02-139">将当前版本的 [MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) 应用程序的源代码下载到系统上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-139">Download the source code for the current version of the [MFCMAPI](https://go.microsoft.com/fwlink/?LinkID=124154) application to a folder on your system.</span></span> 
    
2. <span data-ttu-id="27d02-140">将 MFCMAPI 更改 _集_.zip文件解压缩到硬盘驱动器上的空文件夹。</span><span class="sxs-lookup"><span data-stu-id="27d02-140">Extract the files in MFCMAPI- _changeset_.zip to an empty folder on your hard drive.</span></span>
    
3. <span data-ttu-id="27d02-141">打开 MFCMapi 项目 (\ _foldername_\ MFCMapi.vcproj) 中Visual Studio检查源代码。</span><span class="sxs-lookup"><span data-stu-id="27d02-141">Open the MFCMapi project (\ _foldername_\ MFCMapi.vcproj) in Visual Studio to examine the source code.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="27d02-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27d02-142">See also</span></span>

- [<span data-ttu-id="27d02-143">创建简单邮件项目</span><span class="sxs-lookup"><span data-stu-id="27d02-143">Create a Simple Mail Item</span></span>](how-to-create-a-simple-mail-item.md)
- [<span data-ttu-id="27d02-144">创建简单重复性任务项</span><span class="sxs-lookup"><span data-stu-id="27d02-144">Create a Simple Recurrent Task Item</span></span>](how-to-create-a-simple-recurrent-task-item.md)
- [<span data-ttu-id="27d02-145">创建复杂定期约会项目</span><span class="sxs-lookup"><span data-stu-id="27d02-145">Create a Complex Recurrent Appointment Item</span></span>](how-to-create-a-complex-recurrent-appointment-item.md)
- [<span data-ttu-id="27d02-146">读取和分析定期模式</span><span class="sxs-lookup"><span data-stu-id="27d02-146">Read and Parse a Recurrence Pattern</span></span>](how-to-read-and-parse-a-recurrence-pattern.md)

