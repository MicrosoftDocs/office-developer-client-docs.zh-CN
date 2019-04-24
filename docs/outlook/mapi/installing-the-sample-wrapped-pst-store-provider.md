---
title: 安装示例包装的 PST 存储区提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 90ce0ea3-ba73-cb57-0fa9-8898bc4ac9de
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: a1574de555eb74d06c4dbe721e7e013ac59d3071
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309630"
---
# <a name="installing-the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="5f65d-103">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-103">Installing the Sample Wrapped PST Store Provider</span></span>

  
  
<span data-ttu-id="5f65d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f65d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f65d-105">本主题将指导您完成下载和安装包装的 PST 存储提供程序示例的步骤。</span><span class="sxs-lookup"><span data-stu-id="5f65d-105">This topic takes you through the steps to download and install the Sample Wrapped PST Store Provider.</span></span> <span data-ttu-id="5f65d-106">示例包装的 pst 存储区提供程序 WrapPST 实现了一个打包的 pst 存储提供程序, 该提供程序将与复制 API 结合使用。</span><span class="sxs-lookup"><span data-stu-id="5f65d-106">The Sample Wrapped PST Store Provider, WrapPST, implements a wrapped PST store provider that is intended to be used in conjunction with the Replication API.</span></span> <span data-ttu-id="5f65d-107">有关复制 api 的详细信息, 请参阅[关于复制 api](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="5f65d-107">For more information about the Replication API, see [About the Replication API](about-the-replication-api.md).</span></span>
  
## <a name="install-the-sample-wrapped-pst-store-provider"></a><span data-ttu-id="5f65d-108">安装示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-108">Install the Sample Wrapped PST Store Provider</span></span>

1. <span data-ttu-id="5f65d-109">若要下载示例包装的 PST 存储区提供程序, 请参阅[Outlook 2007 辅助参考代码示例和可再发行安装程序](https://www.microsoft.com/en-us/download/details.aspx?id=24102)。</span><span class="sxs-lookup"><span data-stu-id="5f65d-109">To download the Sample Wrapped PST Store Provider, see [Outlook 2007 Auxiliary Reference Code Samples and Redistributable Installer](https://www.microsoft.com/en-us/download/details.aspx?id=24102).</span></span>
    
2. <span data-ttu-id="5f65d-110">打开 " **SampleWrappedPSTStoreProvider** " 文件夹, 然后单击 "**提取所有文件**"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-110">Open the **SampleWrappedPSTStoreProvider** folder and click **Extract All Files**.</span></span>
    
3. <span data-ttu-id="5f65d-111">单击 "**浏览**", 选择要保存示例的位置, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5f65d-111">Click **Browse**, select the location where you want to save the sample, and click **OK**.</span></span>
    
4. <span data-ttu-id="5f65d-112">单击“提取”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5f65d-112">Click **Extract**.</span></span> <span data-ttu-id="5f65d-113">此时将显示所选的文件夹, 其中包含已提取的文件。</span><span class="sxs-lookup"><span data-stu-id="5f65d-113">The folder you selected appears and contains the extracted files.</span></span>
    
5. <span data-ttu-id="5f65d-114">以管理员身份打开 Visual Studio 2005。</span><span class="sxs-lookup"><span data-stu-id="5f65d-114">Open Visual Studio 2005 as an administrator.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f65d-115">如果您的计算机运行的是 Windows XP, 则必须以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="5f65d-115">If your computer is running Windows XP, you must be logged in as an Administrator.</span></span> <span data-ttu-id="5f65d-116">如果你的计算机运行的是 Windows Vista, 则必须以管理员身份登录, 然后才能右键单击 Visual Studio 2005 图标并单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-116">If your computer is running Windows Vista, you must be logged in as an Administrator and you must right-click the Visual Studio 2005 icon and click **Run as administrator**.</span></span> 
  
6. <span data-ttu-id="5f65d-117">在 Visual Studio 2005 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-117">In Visual Studio 2005, click **File**, select **Open**, and then click **Project/Solution**.</span></span>
    
7. <span data-ttu-id="5f65d-118">浏览到保存示例的位置, 单击 " **WrapPST**", 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-118">Browse to the location where you saved the sample, click **WrapPST**, and then click **Open**.</span></span>
    
8. <span data-ttu-id="5f65d-119">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-119">On the **Build** menu, click **Build Solution**.</span></span>
    
9. <span data-ttu-id="5f65d-120">在 "**将文件另存为**" 对话框中, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-120">In the **Save File As** dialog box, click **Save**.</span></span>
    
10. <span data-ttu-id="5f65d-121">在保存该示例的文件夹中, 右键单击该 **.bat**文件, 然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="5f65d-121">In the folder where you saved the sample, right-click the **Install.bat** file and click **Run as administrator**.</span></span>
    
11. <span data-ttu-id="5f65d-122">在“用户帐户控制”\*\*\*\* 对话框中，单击“继续”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5f65d-122">In the **User Account Control** dialog box, click **Continue**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5f65d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f65d-123">See also</span></span>



[<span data-ttu-id="5f65d-124">关于示例包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-124">About the Sample Wrapped PST Store Provider</span></span>](about-the-sample-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="5f65d-125">初始化打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-125">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="5f65d-126">登录到打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-126">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="5f65d-127">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-127">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
  
[<span data-ttu-id="5f65d-128">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5f65d-128">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)

