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
ms.openlocfilehash: 4c5b6cbdda63dcb79b23253e0db695ae658c4fa4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775112"
---
# <a name="install-the-samples-used-in-this-section"></a><span data-ttu-id="1f257-103">安装使用本节中的示例</span><span class="sxs-lookup"><span data-stu-id="1f257-103">Install the samples used in this section</span></span>

<span data-ttu-id="1f257-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1f257-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1f257-105">若要安装的 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目查看和运行代码示例[通过使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)部分中的主题引用，请按照下列步骤。</span><span class="sxs-lookup"><span data-stu-id="1f257-105">To install the MFCMAPI application and CreateOutlookItemsAddin project to view and run the sample code referenced by the topics in the [Creating Outlook Items by Using MAPI](creating-outlook-items-by-using-mapi.md) section, follow these steps.</span></span> 

<span data-ttu-id="1f257-106">若要下载并安装在"使用 MAPI 创建 Outlook 项目"中使用的示例部分中，请按照下列步骤。</span><span class="sxs-lookup"><span data-stu-id="1f257-106">To download and install the examples used in the "Using MAPI to create Outlook items" section, follow these steps.</span></span>

### <a name="to-download-and-install-the-mfcmapi-application-and-open-createoutlookitemsaddin-project"></a><span data-ttu-id="1f257-107">若要下载和安装 MFCMAPI 应用程序并打开 CreateOutlookItemsAddin 项目</span><span class="sxs-lookup"><span data-stu-id="1f257-107">To download and install the MFCMAPI application and open CreateOutlookItemsAddin project</span></span>

1. <span data-ttu-id="1f257-108">下载到您的系统上的文件夹的当前版本的可执行[MFCMAPI](http://go.microsoft.com/fwlink/?LinkID=124154) 。</span><span class="sxs-lookup"><span data-stu-id="1f257-108">Download the current version of the [MFCMAPI](http://go.microsoft.com/fwlink/?LinkID=124154) executable to a folder on your system.</span></span> 
    
2. <span data-ttu-id="1f257-109">提取中 MFCMapi.exe MFCMapi.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="1f257-109">Extract the MFCMapi.exe file in MFCMapi.exe.</span></span> <span data-ttu-id="1f257-110">在您的硬盘上的空文件夹_版本_.zip。</span><span class="sxs-lookup"><span data-stu-id="1f257-110">_version_.zip to an empty folder on your hard drive.</span></span>
    
3. <span data-ttu-id="1f257-111">下载[CreateOutlookItemsAddin](http://go.microsoft.com/fwlink/?LinkID=127828)项目的当前版本。</span><span class="sxs-lookup"><span data-stu-id="1f257-111">Download the current version of the [CreateOutlookItemsAddin](http://go.microsoft.com/fwlink/?LinkID=127828) project.</span></span> 
    
4. <span data-ttu-id="1f257-112">提取 CreateOutlookItemsAddin.zip 文件提取到在步骤 2 中的 MFCMapi.exe 文件的文件夹中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="1f257-112">Extract all the files in the CreateOutlookItemsAddin.zip file to the folder where you extracted the MFCMapi.exe file in Step 2.</span></span>
    
5. <span data-ttu-id="1f257-113">从文件夹用于在步骤 2 中生成目录 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\Debug) 复制 MFCMapi.exe。</span><span class="sxs-lookup"><span data-stu-id="1f257-113">Copy MFCMapi.exe from the folder used in Step 2 to the build directory for the CreateOutlookItemsAddin project (\CreateOutlookItemsAddin\Debug).</span></span>
    
6. <span data-ttu-id="1f257-114">要检查的源代码的 Visual Studio 中打开 CreateOutlookItemsAddin 项目 (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj)。</span><span class="sxs-lookup"><span data-stu-id="1f257-114">Open the CreateOutlookItemsAddin project (\CreateOutlookItemsAddin\CreateOutlookItemsAddin.vcproj) in Visual Studio to examine the source code.</span></span> <span data-ttu-id="1f257-115">从[通过使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)部分，以确定哪些源文件以打开参考主题。</span><span class="sxs-lookup"><span data-stu-id="1f257-115">Refer to the topics from the [Creating Outlook Items by Using MAPI](creating-outlook-items-by-using-mapi.md) section to determine which source files to open.</span></span> 
    
## <a name="run-mfcmapi-and-the-createoutlookitemsaddin-project"></a><span data-ttu-id="1f257-116">运行 MFCMAPI 和 CreateOutlookItemsAddin 项目</span><span class="sxs-lookup"><span data-stu-id="1f257-116">Run MFCMAPI and the CreateOutlookItemsAddin project</span></span>

<span data-ttu-id="1f257-117">下面的步骤假定您已下载并安装 MFCMAPI 可执行文件和 CreateOutlookItemsAddin 项目前面过程中所述的当前版本。</span><span class="sxs-lookup"><span data-stu-id="1f257-117">The following steps assume that you have downloaded and installed the current version of the MFCMAPI executable and the CreateOutlookItemsAddin project as described in the preceding procedure.</span></span> <span data-ttu-id="1f257-118">以下步骤将指导您使您能够创建使用 MFCMAPI 应用程序和 CreateOutlookItemsAddin 项目的 Outlook 项目的**加载项**菜单项。</span><span class="sxs-lookup"><span data-stu-id="1f257-118">These steps will guide you to the **Addins** menu items that enable you to create Outlook items using the MFCMAPI application and the CreateOutlookItemsAddin project.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1f257-119">步骤 8 和步骤 9 中选择的命令中选择的文件夹取决于从[通过使用 MAPI 创建 Outlook 项目](creating-outlook-items-by-using-mapi.md)部分的主题之一中讨论的项类型。</span><span class="sxs-lookup"><span data-stu-id="1f257-119">The folder you select in step 8, and the command you select in step 9, depends on the item type discussed in one of the topics from the [Creating Outlook Items by Using MAPI](creating-outlook-items-by-using-mapi.md) section.</span></span> 

### <a name="to-run-the-mfcmapi-application-and-addins-menu-commands"></a><span data-ttu-id="1f257-120">若要运行的 MFCMAPI 应用程序和加载项菜单命令</span><span class="sxs-lookup"><span data-stu-id="1f257-120">To run the MFCMAPI application and Addins menu commands</span></span>

1. <span data-ttu-id="1f257-121">启动 Mfcmapi.exe 按照安装说明时，将创建的 CreateOutlookItemsAddin\Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1f257-121">Start Mfcmapi.exe in the CreateOutlookItemsAddin\Debug folder that is created when you follow the installation instructions.</span></span>
    
2. <span data-ttu-id="1f257-122">单击**确定**以关闭 MFCMAPI 初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="1f257-122">Click **OK** to dismiss the MFCMAPI splash screen.</span></span> 
    
3. <span data-ttu-id="1f257-123">在**会话**菜单中，单击**登录名和显示存储表**。</span><span class="sxs-lookup"><span data-stu-id="1f257-123">On the **Session** menu, click **Logon and Display Store Table**.</span></span>
    
4. <span data-ttu-id="1f257-124">在**选择配置文件**对话框中，选择正确的配置文件，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="1f257-124">In the **Choose Profile** dialog box, select the correct profile, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="1f257-125">双击存储表的列表视图中的**邮箱- _[用户名]_ ** 。</span><span class="sxs-lookup"><span data-stu-id="1f257-125">Double-click **Mailbox -  _[User Name]_** in the store table list view.</span></span> 
    
6. <span data-ttu-id="1f257-126">在文件夹树视图中，展开根节点。</span><span class="sxs-lookup"><span data-stu-id="1f257-126">In the folder tree view, expand the root node.</span></span> <span data-ttu-id="1f257-127">显示的根节点取决于所选的配置文件的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="1f257-127">The name displayed for the root node varies depending on the type of profile selected.</span></span> <span data-ttu-id="1f257-128">此节点通常显示为**根-邮箱**。</span><span class="sxs-lookup"><span data-stu-id="1f257-128">Typically this node is displayed as **Root - Mailbox**.</span></span>
    
7. <span data-ttu-id="1f257-129">在文件夹树视图中，展开包含的信息存储节点。</span><span class="sxs-lookup"><span data-stu-id="1f257-129">In the folder tree view, expand the node that contains the information store.</span></span> <span data-ttu-id="1f257-130">显示为此节点取决于所选的配置文件的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="1f257-130">The name displayed for this node varies depending on the type of profile selected.</span></span> <span data-ttu-id="1f257-131">通常为**IPM_SUBTREE**或**信息存储的顶部**显示此节点。</span><span class="sxs-lookup"><span data-stu-id="1f257-131">Typically this node is displayed as **IPM_SUBTREE** or **Top of Information Store**.</span></span>
    
8. <span data-ttu-id="1f257-132">双击要创建的项目类型的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f257-132">Double-click the folder for the item type to create.</span></span> <span data-ttu-id="1f257-133">例如，若要创建约会，请单击**约会**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f257-133">For example, to create an appointment, click the **Appointments** folder.</span></span> 
    
9. <span data-ttu-id="1f257-134">在**外接程序**菜单中，单击项目创建适当的命令。</span><span class="sxs-lookup"><span data-stu-id="1f257-134">On the **Addins** menu, click the appropriate command for the item to create.</span></span> 
    
## <a name="download-and-view-code-from-the-mfcmapi-application"></a><span data-ttu-id="1f257-135">下载并查看 MFCMAPI 应用程序的代码</span><span class="sxs-lookup"><span data-stu-id="1f257-135">Download and view code from the MFCMAPI application</span></span>

<span data-ttu-id="1f257-136">某些主题引用 MFCMAPI 应用程序本身的源代码。</span><span class="sxs-lookup"><span data-stu-id="1f257-136">Some topics refer to source code from the MFCMAPI application itself.</span></span> <span data-ttu-id="1f257-137">以下步骤介绍如何下载 MFCMAPI 源代码和 Visual Studio 中进行查看。</span><span class="sxs-lookup"><span data-stu-id="1f257-137">The following steps describe how to download the MFCMAPI source code and view it in Visual Studio.</span></span> 

### <a name="to-download-and-view-the-mfcmapi-application-source-code"></a><span data-ttu-id="1f257-138">下载并查看 MFCMAPI 应用程序的源代码</span><span class="sxs-lookup"><span data-stu-id="1f257-138">To download and view the MFCMAPI application source code</span></span>

1. <span data-ttu-id="1f257-139">下载到您的系统上的文件夹的[MFCMAPI](http://go.microsoft.com/fwlink/?LinkID=124154)应用程序的当前版本的源代码。</span><span class="sxs-lookup"><span data-stu-id="1f257-139">Download the source code for the current version of the [MFCMAPI](http://go.microsoft.com/fwlink/?LinkID=124154) application to a folder on your system.</span></span> 
    
2. <span data-ttu-id="1f257-140">在您的硬盘上的空文件夹 MFCMAPI-_变更集_.zip 文件提取。</span><span class="sxs-lookup"><span data-stu-id="1f257-140">Extract the files in MFCMAPI- _changeset_.zip to an empty folder on your hard drive.</span></span>
    
3. <span data-ttu-id="1f257-141">打开 MFCMapi 项目 (\_文件夹名称_\ MFCMapi.vcproj) 在 Visual Studio 中检查的源代码。</span><span class="sxs-lookup"><span data-stu-id="1f257-141">Open the MFCMapi project (\ _foldername_\ MFCMapi.vcproj) in Visual Studio to examine the source code.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f257-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f257-142">See also</span></span>

- [<span data-ttu-id="1f257-143">创建简单邮件项</span><span class="sxs-lookup"><span data-stu-id="1f257-143">Create a Simple Mail Item</span></span>](how-to-create-a-simple-mail-item.md)
- [<span data-ttu-id="1f257-144">创建简单重复任务项</span><span class="sxs-lookup"><span data-stu-id="1f257-144">Create a Simple Recurrent Task Item</span></span>](how-to-create-a-simple-recurrent-task-item.md)
- [<span data-ttu-id="1f257-145">创建复杂重复约会项</span><span class="sxs-lookup"><span data-stu-id="1f257-145">Create a Complex Recurrent Appointment Item</span></span>](how-to-create-a-complex-recurrent-appointment-item.md)
- [<span data-ttu-id="1f257-146">读取和分析定期模式</span><span class="sxs-lookup"><span data-stu-id="1f257-146">Read and Parse a Recurrence Pattern</span></span>](how-to-read-and-parse-a-recurrence-pattern.md)

