---
title: MFCMAPI 作为的代码示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f98eb842-fe76-4f60-b5e2-d2217d1a66ad
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc92cc8deb3d12c4bc8fca4c680fd4a675b4a578
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776507"
---
# <a name="mfcmapi-as-a-code-sample"></a><span data-ttu-id="132ca-103">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="132ca-103">MFCMAPI as a code sample</span></span>
 
<span data-ttu-id="132ca-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="132ca-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="132ca-105">MFCMAPI 示例使用消息 API 来提供对通过图形用户界面的 MAPI 存储的访问。</span><span class="sxs-lookup"><span data-stu-id="132ca-105">The MFCMAPI sample uses the Messaging API to provide access to MAPI stores through a graphical user interface.</span></span> <span data-ttu-id="132ca-106">下载此示例之后，您可以使用的源文件要检查的许多 MAPI 接口和引用的示例使用情况。</span><span class="sxs-lookup"><span data-stu-id="132ca-106">After you download this sample, you can use the source files to examine example usage cases for many of the MAPI interfaces and references.</span></span> <span data-ttu-id="132ca-107">有关详细信息，请参阅[MAPI 接口](mapi-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="132ca-107">For more information, see [MAPI Interfaces](mapi-interfaces.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="132ca-108">平台：</span><span class="sxs-lookup"><span data-stu-id="132ca-108">Platforms:</span></span>  <br/> |<span data-ttu-id="132ca-109">Microsoft Visual Studio 2008 编译为 Windows 7、 Windows Vista、 Windows Server 2008、 Windows XP SP2 和 Windows Server 2003 SP1</span><span class="sxs-lookup"><span data-stu-id="132ca-109">Microsoft Visual Studio 2008 to compile for Windows 7, Windows Vista, Windows Server 2008, Windows XP SP2, and Windows Server 2003 SP1</span></span>  <br/> |
   
### <a name="to-download-mfcmapi"></a><span data-ttu-id="132ca-110">若要下载 MFCMAPI</span><span class="sxs-lookup"><span data-stu-id="132ca-110">To download MFCMAPI</span></span>
  
1. <span data-ttu-id="132ca-111">在[MFCMAPI](http://codeplex.com/MFCMAPI)页上，单击**源代码**选项卡。</span><span class="sxs-lookup"><span data-stu-id="132ca-111">On the [MFCMAPI](http://codeplex.com/MFCMAPI) page, click the **Source Code** tab.</span></span> 
    
2. <span data-ttu-id="132ca-112">在**最近的签入**下的最新的生成单击**下载**。</span><span class="sxs-lookup"><span data-stu-id="132ca-112">Under **Recent Check-Ins**, click **Download** for the most recent build.</span></span> 
    
3. <span data-ttu-id="132ca-113">阅读许可协议，，，然后单击**我同意**。</span><span class="sxs-lookup"><span data-stu-id="132ca-113">Read the license agreement, and then click **I Agree**.</span></span>
    
4. <span data-ttu-id="132ca-114">在**文件下载**对话框中，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="132ca-114">In the **File Download** dialog box, click **Save**.</span></span> <span data-ttu-id="132ca-115">在**另存为**对话框中，找到您要在其中保存源文件的文件夹，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="132ca-115">In the **Save As** dialog box, locate the folder in which you want to save the source files, and then click **Save**.</span></span>
    
5. <span data-ttu-id="132ca-116">在**下载完毕**对话框中，单击**打开文件夹**。</span><span class="sxs-lookup"><span data-stu-id="132ca-116">In the **Download Complete** dialog box, click **Open Folder**.</span></span> <span data-ttu-id="132ca-117">您还可以单击**关闭**以关闭对话框并保存其文件夹中找到的压缩的源文件。</span><span class="sxs-lookup"><span data-stu-id="132ca-117">You can also click **Close** to close the dialog box and locate the zipped source files in the folder that you saved them in.</span></span> 
    
6. <span data-ttu-id="132ca-118">右键单击**MFCMAPI-\<版本号\>.zip**文件，，然后单击**全部提取**。</span><span class="sxs-lookup"><span data-stu-id="132ca-118">Right-click the **MFCMAPI-\<version number\>.zip** file, and then click **Extract All**.</span></span> <span data-ttu-id="132ca-119">在出现的对话框中，单击**提取**以将文件提取到的文件夹的显示。</span><span class="sxs-lookup"><span data-stu-id="132ca-119">In the dialog box that appears, click **Extract** to extract the files to the folder that is displayed.</span></span> <span data-ttu-id="132ca-120">您还可以单击**浏览**以选择或创建不同的文件夹。</span><span class="sxs-lookup"><span data-stu-id="132ca-120">You can also click **Browse** to select or create a different folder.</span></span> 
    
7. <span data-ttu-id="132ca-121">以管理员身份运行 Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="132ca-121">Run Visual Studio 2008 as an administrator.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="132ca-122">如果您的计算机运行 Windows XP，您必须以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="132ca-122">If your computer is running Windows XP, you must be logged in as an administrator.</span></span> <span data-ttu-id="132ca-123">如果您的计算机运行 Windows Vista，您必须以管理员身份登录，您必须右键单击 Visual Studio 2008 图标，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="132ca-123">If your computer is running Windows Vista, you must be logged in as an administrator and you must right-click the Visual Studio 2008 icon and then click **Run as administrator**.</span></span> 
  
8. <span data-ttu-id="132ca-124">在 Visual Studio 2008 中，单击**文件**，指向**打开**，，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="132ca-124">In Visual Studio 2008, click **File**, point to **Open**, and then click **Project/Solution**.</span></span>
    
9. <span data-ttu-id="132ca-125">浏览到保存该示例的位置，选择**MFCMapi.vcproj**，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="132ca-125">Browse to the location where you saved the sample, select **MFCMapi.vcproj**, and then click **Open**.</span></span>
    
10. <span data-ttu-id="132ca-126">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="132ca-126">On the **Build** menu, click **Build Solution**.</span></span>
    
11. <span data-ttu-id="132ca-127">在**将文件另存为**对话框中，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="132ca-127">In the **Save File As** dialog box, click **Save**.</span></span>
    
### <a name="to-use-mfcmapi-as-a-code-sample"></a><span data-ttu-id="132ca-128">使用 MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="132ca-128">To use MFCMAPI as a code sample</span></span>
  
<span data-ttu-id="132ca-129">在**解决方案资源管理器**中，展开**MFCMapi**项目，并检查编程方案**头文件**、**资源文件**和**源文件**节点中的文件。</span><span class="sxs-lookup"><span data-stu-id="132ca-129">In **Solution Explorer**, expand the **MFCMapi** project and examine the files in the **Header Files**, **Resource Files**, and **Source Files** nodes for programming scenarios.</span></span> 
  
<span data-ttu-id="132ca-130">在[MAPI 接口](mapi-interfaces.md)部分中的许多方法主题指向 MFCMAPI 源文件的编程示例。</span><span class="sxs-lookup"><span data-stu-id="132ca-130">Many method topics in the [MAPI Interfaces](mapi-interfaces.md) section point to MFCMAPI source files for programming examples.</span></span> <span data-ttu-id="132ca-131">例如，在[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)指示可以这样看待函数`CMsgStoreDlg::OnDisplayReceiveFolderTable`MsgStoreDlg.cpp 文件中。</span><span class="sxs-lookup"><span data-stu-id="132ca-131">For example, in [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) you are instructed to look at the function  `CMsgStoreDlg::OnDisplayReceiveFolderTable` in the MsgStoreDlg.cpp file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="132ca-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="132ca-132">See also</span></span>

- [<span data-ttu-id="132ca-133">MAPI 示例（英文）</span><span class="sxs-lookup"><span data-stu-id="132ca-133">MAPI Samples</span></span>](mapi-samples.md)

