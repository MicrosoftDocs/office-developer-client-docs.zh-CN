---
title: 安装示例脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1b6ae6c-dcf2-a07f-c417-3a1049b758ad
description: '上次修改时间: 2006 年7月2012'
ms.openlocfilehash: b7b9ce539537e0759020ef7e3b4f6541a940d6fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317211"
---
# <a name="installing-the-sample-offline-state-add-in"></a><span data-ttu-id="96c76-103">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="96c76-103">Installing the Sample Offline State Add-in</span></span>

  
  
<span data-ttu-id="96c76-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="96c76-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="96c76-105">本主题将指导您完成下载和安装示例脱机状态加载项的步骤。</span><span class="sxs-lookup"><span data-stu-id="96c76-105">This topic takes you through the steps to download and install the Sample Offline State Add-in.</span></span> <span data-ttu-id="96c76-106">示例脱机状态外接程序是一个 COM 加载项, 它将**脱机状态**菜单添加到 Outlook 并利用脱机状态 API。</span><span class="sxs-lookup"><span data-stu-id="96c76-106">The Sample Offline State Add-in is a COM add-in that adds an **Offline State** menu to Outlook and utilizes the Offline State API.</span></span> <span data-ttu-id="96c76-107">通过脱机状态菜单, 您可以启用或禁用状态监视、检查当前状态并更改当前状态。</span><span class="sxs-lookup"><span data-stu-id="96c76-107">Through the Offline State menu you can enable or disable state monitoring, check the current state, and change the current state.</span></span> <span data-ttu-id="96c76-108">有关如何实现脱机状态外接程序的详细信息, 请参阅[设置脱机状态外接程序](setting-up-an-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="96c76-108">For more information about how the Offline State Add-in is implemented, see [Setting Up an Offline State Add-in](setting-up-an-offline-state-add-in.md).</span></span>
  
## <a name="install-the-sample-offline-state-add-in"></a><span data-ttu-id="96c76-109">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="96c76-109">Install the Sample Offline State Add-in</span></span>

1. <span data-ttu-id="96c76-110">在此处下载示例脱机状态外接程序: [Outlook 2007 辅助参考代码示例和可再发行安装程序](https://www.microsoft.com/en-us/download/details.aspx?id=24102)。</span><span class="sxs-lookup"><span data-stu-id="96c76-110">Download the Sample Offline State Add-in here: [Outlook 2007 Auxiliary Reference Code Samples and Redistributable Installer](https://www.microsoft.com/en-us/download/details.aspx?id=24102).</span></span>
    
2. <span data-ttu-id="96c76-111">以管理员身份运行 Visual Studio 2005。</span><span class="sxs-lookup"><span data-stu-id="96c76-111">Run Visual Studio 2005 as an administrator.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="96c76-112">如果您的计算机运行的是 Windows XP, 则必须以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="96c76-112">If your computer is running Windows XP, you must be logged in as an Administrator.</span></span> <span data-ttu-id="96c76-113">如果您的计算机运行的是 Windows Vista, 则必须以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="96c76-113">If your computer is running Windows Vista, you must be logged in as an Administrator.</span></span> <span data-ttu-id="96c76-114">右键单击 "Visual Studio 2005" 图标, 然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="96c76-114">Right-click the Visual Studio 2005 icon and click **Run as administrator**.</span></span> 
  
3. <span data-ttu-id="96c76-115">在 Visual Studio 2005 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="96c76-115">In Visual Studio 2005, click **File**, select **Open**, and then click **Project/Solution**.</span></span>
    
4. <span data-ttu-id="96c76-116">浏览到保存示例的位置, 单击 " **ConnectionStateAddin**", 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="96c76-116">Browse to the location where you saved the sample, click **ConnectionStateAddin**, and then click **Open**.</span></span>
    
5. <span data-ttu-id="96c76-117">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="96c76-117">On the **Build** menu, click **Build Solution**.</span></span>
    
6. <span data-ttu-id="96c76-118">在 "**将文件另存为**" 对话框中, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="96c76-118">In the **Save File As** dialog box, click **Save**.</span></span>
    
7. <span data-ttu-id="96c76-119">依次单击 "**开始**" 菜单、"**所有程序**"、"**附件**", 右键单击 "**命令提示符**", 然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="96c76-119">Click the **Start** menu, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="96c76-120">如果您运行的是 Windows XP, 则必须以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="96c76-120">If you are running Windows XP, you must be logged in as an Administrator.</span></span> 
  
8. <span data-ttu-id="96c76-121">在“用户帐户控制”\*\*\*\* 对话框中，单击“继续”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96c76-121">In the **User Account Control** dialog box, click **Continue**.</span></span>
    
9. <span data-ttu-id="96c76-122">在**命令提示符**窗口中, 将目录更改为保存示例的调试文件夹。</span><span class="sxs-lookup"><span data-stu-id="96c76-122">In the **Command Prompt** window, change directories to the Debug folder where you saved the sample.</span></span> <span data-ttu-id="96c76-123">例如, 如果您将示例保存在 C:\ 上驱动器, 请键入**cd "C:\ConnectionStateAddin\Debug"** , 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="96c76-123">For example, if you saved the sample on your C:\ drive, you would type **cd "C:\ConnectionStateAddin\Debug"** and then press **ENTER**.</span></span> 
    
10. <span data-ttu-id="96c76-124">键入**regsvr32 OfflineStateAddin** , 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="96c76-124">Type **regsvr32 OfflineStateAddin.dll** and press **ENTER**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="96c76-125">若要卸载示例脱机状态加载项, 请键入**regsvr32-u OfflineStateAddin**</span><span class="sxs-lookup"><span data-stu-id="96c76-125">To uninstall the Sample Offline State Add-in, type **regsvr32 -u OfflineStateAddin.dll**</span></span>
  
11. <span data-ttu-id="96c76-126">在 " **RegSrv32** " 对话框中, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="96c76-126">In the **RegSrv32** dialog box, click **OK**.</span></span>
    
12. <span data-ttu-id="96c76-127">重新启动 Outlook 以查看**脱机状态**菜单。</span><span class="sxs-lookup"><span data-stu-id="96c76-127">Restart Outlook to see the **Offline State** menu.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="96c76-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96c76-128">See also</span></span>



[<span data-ttu-id="96c76-129">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="96c76-129">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="96c76-130">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="96c76-130">Installing the Sample Offline State Add-in</span></span>](installing-the-sample-offline-state-add-in.md)
  
[<span data-ttu-id="96c76-131">关于示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="96c76-131">About the Sample Offline State Add-in</span></span>](about-the-sample-offline-state-add-in.md)
  
[<span data-ttu-id="96c76-132">设置脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="96c76-132">Setting Up an Offline State Add-in</span></span>](setting-up-an-offline-state-add-in.md)
  
[<span data-ttu-id="96c76-133">使用脱机状态加载项监视连接状态更改</span><span class="sxs-lookup"><span data-stu-id="96c76-133">Monitoring Connection State Changes Using an Offline State Add-in</span></span>](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
  
[<span data-ttu-id="96c76-134">断开与脱机状态外接程序的连接</span><span class="sxs-lookup"><span data-stu-id="96c76-134">Disconnecting an Offline State Add-in</span></span>](disconnecting-an-offline-state-add-in.md)

