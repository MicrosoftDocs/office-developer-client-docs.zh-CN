---
title: 邮件存储提供程序示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f1e4077b-7a95-440d-a326-a8dc9cdab4fe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eb51881aac6e1953a21686857944ba2a15d0dca2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436865"
---
# <a name="message-store-provider-sample"></a><span data-ttu-id="8d6c4-103">邮件存储提供程序示例</span><span class="sxs-lookup"><span data-stu-id="8d6c4-103">Message Store Provider Sample</span></span>

  
  
<span data-ttu-id="8d6c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8d6c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8d6c4-105">示例包装的 PST 存储区提供程序使用个人文件夹文件 (PST) 提供程序作为存储数据的后端。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-105">The Sample Wrapped PST Store Provider uses a Personal Folders file (PST) provider as the back end for storing data.</span></span> <span data-ttu-id="8d6c4-106">包装的 PST 存储区提供程序应与复制 API 一起使用。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-106">The wrapped PST store provider should be used together with the Replication API.</span></span> 
  
<span data-ttu-id="8d6c4-107">复制 API 使您能够将项目从后端数据存储库复制到 Microsoft Outlook PST 存储。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-107">The Replication API enables you to replicate items from a back-end data repository into a Microsoft Outlook PST store.</span></span> <span data-ttu-id="8d6c4-108">您可以使用复制 API 将数据复制到专用的 PST 存储, 并跟踪同步状态。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-108">You use the Replication API to replicate the data into a dedicated PST store and keep track of the synchronization state.</span></span> <span data-ttu-id="8d6c4-109">有关详细信息, 请参阅[关于复制 API](about-the-replication-api.md)。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-109">For more information, see [About the Replication API](about-the-replication-api.md).</span></span>
  
<span data-ttu-id="8d6c4-110">示例包装的 pst 存储提供程序中的大多数函数将其参数直接传递给基础 PST 提供程序。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-110">Most of the functions in the Sample Wrapped PST Store Provider pass their arguments directly to the underlying PST provider.</span></span> <span data-ttu-id="8d6c4-111">某些函数需要特殊实现, 以下主题对此进行了说明。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-111">Certain functions require special implementation and are described in the following topics.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8d6c4-112">执行</span><span class="sxs-lookup"><span data-stu-id="8d6c4-112">Executable:</span></span>  <br/> |<span data-ttu-id="8d6c4-113">WrpPST32</span><span class="sxs-lookup"><span data-stu-id="8d6c4-113">WrpPST32.dll</span></span>  <br/> |
|<span data-ttu-id="8d6c4-114">源代码目录:</span><span class="sxs-lookup"><span data-stu-id="8d6c4-114">Source code directory:</span></span>  <br/> |<span data-ttu-id="8d6c4-115">SampleWrappedPSTStoreProvider\WrapPST</span><span class="sxs-lookup"><span data-stu-id="8d6c4-115">SampleWrappedPSTStoreProvider\WrapPST</span></span>  <br/> |
|<span data-ttu-id="8d6c4-116">语言</span><span class="sxs-lookup"><span data-stu-id="8d6c4-116">Language:</span></span>  <br/> |<span data-ttu-id="8d6c4-117">c</span><span class="sxs-lookup"><span data-stu-id="8d6c4-117">C++</span></span>  <br/> |
|<span data-ttu-id="8d6c4-118">平台</span><span class="sxs-lookup"><span data-stu-id="8d6c4-118">Platforms:</span></span>  <br/> |<span data-ttu-id="8d6c4-119">Microsoft Visual Studio 2008 for windows Vista、windows server 2008、windows XP SP2 和 windows Server 2003 SP1 的编译</span><span class="sxs-lookup"><span data-stu-id="8d6c4-119">Microsoft Visual Studio 2008 to compile for Windows Vista, Windows Server 2008, Windows XP SP2, and Windows Server 2003 SP1</span></span>  <br/> |
   
## <a name="supported-features"></a><span data-ttu-id="8d6c4-120">支持的功能</span><span class="sxs-lookup"><span data-stu-id="8d6c4-120">Supported Features</span></span>

<span data-ttu-id="8d6c4-121">此示例支持 Microsoft outlook 2010 64 位, 现已针对 Outlook 2013 进行了修订。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-121">This sample supports Microsoft Outlook 2010 64-bit and has now been revised for Outlook 2013.</span></span> <span data-ttu-id="8d6c4-122">有关其他信息, 请参阅以下主题:</span><span class="sxs-lookup"><span data-stu-id="8d6c4-122">See the following topics for additional information:</span></span>
  
- [<span data-ttu-id="8d6c4-123">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="8d6c4-123">About the Replication API</span></span>](about-the-replication-api.md)
    
- [<span data-ttu-id="8d6c4-124">初始化打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="8d6c4-124">Initializing a Wrapped PST Store Provider</span></span>](initializing-a-wrapped-pst-store-provider.md)
    
- [<span data-ttu-id="8d6c4-125">登录到打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="8d6c4-125">Logging On to a Wrapped PST Store Provider</span></span>](logging-on-to-a-wrapped-pst-store-provider.md)
    
- [<span data-ttu-id="8d6c4-126">使用包装的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="8d6c4-126">Using a Wrapped PST Store Provider</span></span>](using-a-wrapped-pst-store-provider.md)
    
- [<span data-ttu-id="8d6c4-127">关闭打包的 PST 存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="8d6c4-127">Shutting Down a Wrapped PST Store Provider</span></span>](shutting-down-a-wrapped-pst-store-provider.md)
    
 <span data-ttu-id="8d6c4-128">**安装示例包装的 PST 存储区提供程序**</span><span class="sxs-lookup"><span data-stu-id="8d6c4-128">**To install the Sample Wrapped PST Store Provider**</span></span>
  
1. <span data-ttu-id="8d6c4-129">若要下载示例打包的 PST 提供程序, 请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-129">To download the Sample Wrapped PST Provider, see [Downloading the Outlook MAPI Samples](downloading-the-outlook-mapi-samples.md).</span></span>
    
2. <span data-ttu-id="8d6c4-130">找到保存 Outlook MAPI 示例的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-130">Locate the folder where you saved the Outlook MAPI Samples.</span></span> <span data-ttu-id="8d6c4-131">右键单击 " **OutlookMAPISamples\<\>号码**" zip 文件夹, 然后单击 "**全部提取**"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-131">Right-click the **OutlookMAPISamples-\<version number\>** zip folder and then click **Extract All**.</span></span>
    
3. <span data-ttu-id="8d6c4-132">单击 "**浏览**", 选择要保存示例的位置, 然后单击 "**提取**"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-132">Click **Browse**, select the location where you want to save the sample, and then click **Extract**.</span></span>
    
4. <span data-ttu-id="8d6c4-133">运行 Microsoft Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-133">Run Microsoft Visual Studio 2008.</span></span>
    
5. <span data-ttu-id="8d6c4-134">在 Microsoft Visual Studio 2008 中, 单击 "**文件**", 选择 "**打开**", 然后单击 "**项目/解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-134">In Microsoft Visual Studio 2008, click **File**, select **Open**, and then click **Project/Solution**.</span></span>
    
6. <span data-ttu-id="8d6c4-135">浏览到保存示例的位置, 单击 " **WrapPST**", 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-135">Browse to the location where you saved the sample, click **WrapPST.vcproj**, and then click **Open**.</span></span>
    
7. <span data-ttu-id="8d6c4-136">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-136">On the **Build** menu, click **Build Solution**.</span></span>
    
8. <span data-ttu-id="8d6c4-137">在 "**将文件另存为**" 对话框中, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-137">In the **Save File As** dialog box, click **Save**.</span></span>
    
9. <span data-ttu-id="8d6c4-138">在保存示例的文件夹中, 右键单击 **.bat**文件, 然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-138">In the folder where you saved the sample, right-click the **install.bat** file and then click **Run as administrator**.</span></span>
    
10. <span data-ttu-id="8d6c4-139">在“用户帐户控制”\*\*\*\* 对话框中，单击“继续”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8d6c4-139">In the **User Account Control** dialog box, click **Continue**.</span></span>
    

