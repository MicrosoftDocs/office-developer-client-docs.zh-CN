---
title: 作为代码示例的 MFCMAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f98eb842-fe76-4f60-b5e2-d2217d1a66ad
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d72c224db8b3ae4bb6fee3d34f73d9949cda6b8d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356859"
---
# <a name="mfcmapi-as-a-code-sample"></a><span data-ttu-id="39a6e-103">作为代码示例的 MFCMAPI</span><span class="sxs-lookup"><span data-stu-id="39a6e-103">MFCMAPI as a code sample</span></span>
 
<span data-ttu-id="39a6e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="39a6e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="39a6e-105">MFCMAPI 示例使用消息传递 API 通过图形用户界面提供对 MAPI 存储的访问权限。</span><span class="sxs-lookup"><span data-stu-id="39a6e-105">The MFCMAPI sample uses the Messaging API to provide access to MAPI stores through a graphical user interface.</span></span> <span data-ttu-id="39a6e-106">下载此示例后，可以使用源文件检查许多 MAPI 接口和引用的示例用例。</span><span class="sxs-lookup"><span data-stu-id="39a6e-106">After you download this sample, you can use the source files to examine example usage cases for many of the MAPI interfaces and references.</span></span> <span data-ttu-id="39a6e-107">有关详细信息，请参阅 [MAPI Interfaces](mapi-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="39a6e-107">For more information, see [MAPI Interfaces](mapi-interfaces.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="39a6e-108">平台：</span><span class="sxs-lookup"><span data-stu-id="39a6e-108">Platforms:</span></span>  <br/> |<span data-ttu-id="39a6e-109">Microsoft Visual Studio 2008 针对 Windows 7、Windows Vista、Windows Server 2008、Windows XP SP2 和 Windows Server 2003 SP1 进行编译</span><span class="sxs-lookup"><span data-stu-id="39a6e-109">Microsoft Visual Studio 2008 to compile for Windows 7, Windows Vista, Windows Server 2008, Windows XP SP2, and Windows Server 2003 SP1</span></span>  <br/> |
   
### <a name="to-download-mfcmapi"></a><span data-ttu-id="39a6e-110">下载 MFCMAPI</span><span class="sxs-lookup"><span data-stu-id="39a6e-110">To download MFCMAPI</span></span>
  
1. <span data-ttu-id="39a6e-111">在 ["MFCMAPI"](https://codeplex.com/MFCMAPI) 页上，单击" **源代码"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="39a6e-111">On the [MFCMAPI](https://codeplex.com/MFCMAPI) page, click the **Source Code** tab.</span></span> 
    
2. <span data-ttu-id="39a6e-112">在 **"最近签入"下**，单击 **"下载** 最新内部版本"。</span><span class="sxs-lookup"><span data-stu-id="39a6e-112">Under **Recent Check-Ins**, click **Download** for the most recent build.</span></span> 
    
3. <span data-ttu-id="39a6e-113">阅读许可协议，然后单击"**我同意"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-113">Read the license agreement, and then click **I Agree**.</span></span>
    
4. <span data-ttu-id="39a6e-114">在“文件下载”对话框中，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="39a6e-114">In the **File Download** dialog box, click **Save**.</span></span> <span data-ttu-id="39a6e-115">在 **"另存为**"对话框中，找到要保存源文件的文件夹，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-115">In the **Save As** dialog box, locate the folder in which you want to save the source files, and then click **Save**.</span></span>
    
5. <span data-ttu-id="39a6e-116">在"**下载完成"** 对话框中，单击"**打开文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-116">In the **Download Complete** dialog box, click **Open Folder**.</span></span> <span data-ttu-id="39a6e-117">还可以单击 **"关闭** "关闭对话框，并找到保存这些文件的文件夹中的压缩源文件。</span><span class="sxs-lookup"><span data-stu-id="39a6e-117">You can also click **Close** to close the dialog box and locate the zipped source files in the folder that you saved them in.</span></span> 
    
6. <span data-ttu-id="39a6e-118">右键单击 **MFCMAPI- \<.zip\>** 文件，然后单击"全部 **提取"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-118">Right-click the **MFCMAPI-\<version number\>.zip** file, and then click **Extract All**.</span></span> <span data-ttu-id="39a6e-119">在出现的对话框中，单击" **提取** "以将文件解压缩到显示的文件夹。</span><span class="sxs-lookup"><span data-stu-id="39a6e-119">In the dialog box that appears, click **Extract** to extract the files to the folder that is displayed.</span></span> <span data-ttu-id="39a6e-120">也可以单击"浏览 **"** 选择或创建其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="39a6e-120">You can also click **Browse** to select or create a different folder.</span></span> 
    
7. <span data-ttu-id="39a6e-121">以Visual Studio运行 2008 年 6 月。</span><span class="sxs-lookup"><span data-stu-id="39a6e-121">Run Visual Studio 2008 as an administrator.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="39a6e-122">如果计算机在 XP Windows，则必须以管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="39a6e-122">If your computer is running Windows XP, you must be logged in as an administrator.</span></span> <span data-ttu-id="39a6e-123">如果计算机在 Vista Windows，则必须以管理员身份登录，并且必须右键单击 Visual Studio 2008 图标，然后单击"以管理员身份 **运行"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-123">If your computer is running Windows Vista, you must be logged in as an administrator and you must right-click the Visual Studio 2008 icon and then click **Run as administrator**.</span></span> 
  
8. <span data-ttu-id="39a6e-124">在 Visual Studio 2008 中，单击"文件"，指向"打开"，然后单击 **"Project/解决方案"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-124">In Visual Studio 2008, click **File**, point to **Open**, and then click **Project/Solution**.</span></span>
    
9. <span data-ttu-id="39a6e-125">浏览到保存示例的位置，选择 **"MFCMapi.vcproj"，** 然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-125">Browse to the location where you saved the sample, select **MFCMapi.vcproj**, and then click **Open**.</span></span>
    
10. <span data-ttu-id="39a6e-126">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="39a6e-126">On the **Build** menu, click **Build Solution**.</span></span>
    
11. <span data-ttu-id="39a6e-127">在"**将文件另存为**"对话框中，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="39a6e-127">In the **Save File As** dialog box, click **Save**.</span></span>
    
### <a name="to-use-mfcmapi-as-a-code-sample"></a><span data-ttu-id="39a6e-128">使用 MFCMAPI 作为代码示例</span><span class="sxs-lookup"><span data-stu-id="39a6e-128">To use MFCMAPI as a code sample</span></span>
  
<span data-ttu-id="39a6e-129">在 **"解决方案资源管理器**"中，展开 **MFCMapi** 项目并检查"头文件"、"**资源** 文件"和"源文件"节点中的文件，以用于编程方案。 </span><span class="sxs-lookup"><span data-stu-id="39a6e-129">In **Solution Explorer**, expand the **MFCMapi** project and examine the files in the **Header Files**, **Resource Files**, and **Source Files** nodes for programming scenarios.</span></span> 
  
<span data-ttu-id="39a6e-130">MAPI 接口部分 [中的许多](mapi-interfaces.md) 方法主题指向 MFCMAPI 源文件，用于编程示例。</span><span class="sxs-lookup"><span data-stu-id="39a6e-130">Many method topics in the [MAPI Interfaces](mapi-interfaces.md) section point to MFCMAPI source files for programming examples.</span></span> <span data-ttu-id="39a6e-131">例如，在 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 中，会指示您查看  `CMsgStoreDlg::OnDisplayReceiveFolderTable` MsgStoreDlg.cpp 文件中的函数。</span><span class="sxs-lookup"><span data-stu-id="39a6e-131">For example, in [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) you are instructed to look at the function  `CMsgStoreDlg::OnDisplayReceiveFolderTable` in the MsgStoreDlg.cpp file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="39a6e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39a6e-132">See also</span></span>

- [<span data-ttu-id="39a6e-133">MAPI 示例</span><span class="sxs-lookup"><span data-stu-id="39a6e-133">MAPI Samples</span></span>](mapi-samples.md)

