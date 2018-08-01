---
title: 传输提供程序示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ec6eb6c0-bfe3-4989-9071-89a14c0e7bdd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1d0538f02f852580c064560460bb8b2ba54a2f65
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779038"
---
# <a name="transport-provider-sample"></a><span data-ttu-id="6157e-103">传输提供程序示例</span><span class="sxs-lookup"><span data-stu-id="6157e-103">Transport Provider Sample</span></span>

  
  
<span data-ttu-id="6157e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6157e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6157e-105">此示例使用文件和目录传输和接收消息。</span><span class="sxs-lookup"><span data-stu-id="6157e-105">This sample uses files and directories to transmit and receive messages.</span></span> <span data-ttu-id="6157e-106">它实现并注册的非常简单预处理程序将一行文本追加到每个出站邮件。</span><span class="sxs-lookup"><span data-stu-id="6157e-106">It implements and registers a very simple preprocessor that appends a line of text to each outbound message.</span></span> <span data-ttu-id="6157e-107">该示例演示如何拆分传输中性封装格式 (TNEF) 和文本之间的消息内容。</span><span class="sxs-lookup"><span data-stu-id="6157e-107">The sample illustrates how to split message content between Transport Neutral Encapsulation Format (TNEF) and text.</span></span> <span data-ttu-id="6157e-108">它还支持所有配置选项 （属性表、 向导和编程配置） 和消息选项。</span><span class="sxs-lookup"><span data-stu-id="6157e-108">It also supports all configuration options (property sheets, wizards, and programmatic configuration) and message options.</span></span> <span data-ttu-id="6157e-109">它不支持远程传输接口。</span><span class="sxs-lookup"><span data-stu-id="6157e-109">It does not support the remote transport interfaces.</span></span> 
  
<span data-ttu-id="6157e-110">您可以从[Outlook 消息处理 API (MAPI) 代码示例](http://go.microsoft.com/fwlink/?LinkId=129740)下载此示例。</span><span class="sxs-lookup"><span data-stu-id="6157e-110">You can download this sample from [Outlook Messaging API (MAPI) Code Samples](http://go.microsoft.com/fwlink/?LinkId=129740).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6157e-111">可执行文件：</span><span class="sxs-lookup"><span data-stu-id="6157e-111">Executable:</span></span>  <br/> |<span data-ttu-id="6157e-112">mrxp32.dll</span><span class="sxs-lookup"><span data-stu-id="6157e-112">mrxp32.dll</span></span>  <br/> |
|<span data-ttu-id="6157e-113">源代码目录：</span><span class="sxs-lookup"><span data-stu-id="6157e-113">Source code directory:</span></span>  <br/> |<span data-ttu-id="6157e-114">SampleTransportProvider\MRXP</span><span class="sxs-lookup"><span data-stu-id="6157e-114">SampleTransportProvider\MRXP</span></span>  <br/> |
|<span data-ttu-id="6157e-115">语言：</span><span class="sxs-lookup"><span data-stu-id="6157e-115">Language:</span></span>  <br/> |<span data-ttu-id="6157e-116">C++</span><span class="sxs-lookup"><span data-stu-id="6157e-116">C++</span></span>  <br/> |
|<span data-ttu-id="6157e-117">平台：</span><span class="sxs-lookup"><span data-stu-id="6157e-117">Platforms:</span></span>  <br/> |<span data-ttu-id="6157e-118">对于 Windows Vista、 Windows Server 2008、 Windows XP SP2 和 Windows Server 2003 SP1 编译 visual Studio 2008</span><span class="sxs-lookup"><span data-stu-id="6157e-118">Visual Studio 2008 to compile for Windows Vista, Windows Server 2008, Windows XP SP2, and Windows Server 2003 SP1</span></span>  <br/> |
   
## <a name="supported-features"></a><span data-ttu-id="6157e-119">支持的功能</span><span class="sxs-lookup"><span data-stu-id="6157e-119">Supported Features</span></span>

<span data-ttu-id="6157e-120">此示例支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="6157e-120">This sample supports the following features:</span></span>
  
- <span data-ttu-id="6157e-121">如发送、 接收和轮询新邮件的基本功能。</span><span class="sxs-lookup"><span data-stu-id="6157e-121">Basic features such as sending, receiving, and polling for new messages.</span></span>
    
- <span data-ttu-id="6157e-122">交互式和编程方式配置。</span><span class="sxs-lookup"><span data-stu-id="6157e-122">Interactive and programmatic configuration.</span></span>
    
- <span data-ttu-id="6157e-123">除属性设置为**IMAPIStatus**接口。</span><span class="sxs-lookup"><span data-stu-id="6157e-123">The **IMAPIStatus** interface, except for property setting.</span></span> <span data-ttu-id="6157e-124">有关详细信息，请参阅[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="6157e-124">For more information, see the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> 
    
- <span data-ttu-id="6157e-125">线程安全性。</span><span class="sxs-lookup"><span data-stu-id="6157e-125">Thread safety.</span></span>
    
- <span data-ttu-id="6157e-126">事件日志记录到文本文件。</span><span class="sxs-lookup"><span data-stu-id="6157e-126">Event logging to a text file.</span></span> <span data-ttu-id="6157e-127">文件是自动为指定大小限制。</span><span class="sxs-lookup"><span data-stu-id="6157e-127">The file is automatically limited to a specified size.</span></span> <span data-ttu-id="6157e-128">所有传输会话都使用相同的文件。</span><span class="sxs-lookup"><span data-stu-id="6157e-128">All transport sessions use the same file.</span></span>
    
## <a name="unsupported-features"></a><span data-ttu-id="6157e-129">不支持的功能</span><span class="sxs-lookup"><span data-stu-id="6157e-129">Unsupported Features</span></span>

<span data-ttu-id="6157e-130">此示例不支持异步检测的传入消息。</span><span class="sxs-lookup"><span data-stu-id="6157e-130">This sample does not support asynchronous detection of incoming messages.</span></span>
  
 <span data-ttu-id="6157e-131">**安装示例传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="6157e-131">**To install the Sample Transport Provider**</span></span>
  
1. <span data-ttu-id="6157e-132">若要下载示例传输提供程序，请参阅[下载 Outlook MAPI 示例](downloading-the-outlook-mapi-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="6157e-132">To download the Sample Transport Provider, see [Downloading the Outlook MAPI Samples](downloading-the-outlook-mapi-samples.md).</span></span>
    
2. <span data-ttu-id="6157e-133">找到的 Outlook MAPI 示例的保存位置的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6157e-133">Locate the folder where you saved the Outlook MAPI samples.</span></span> <span data-ttu-id="6157e-134">右键单击**OutlookMAPISamples-\<版本号\>** zip 文件夹，然后单击**全部提取**。</span><span class="sxs-lookup"><span data-stu-id="6157e-134">Right-click the **OutlookMAPISamples-\<version number\>** zip folder and click **Extract All**.</span></span>
    
3. <span data-ttu-id="6157e-135">单击**浏览**，选择要用于保存该示例的位置，然后单击**提取**。</span><span class="sxs-lookup"><span data-stu-id="6157e-135">Click **Browse**, select the location where you want to save the sample, and click **Extract**.</span></span>
    
4. <span data-ttu-id="6157e-136">运行 Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="6157e-136">Run Visual Studio 2008.</span></span>
    
5. <span data-ttu-id="6157e-137">在 Visual Studio 2008 中，单击**文件**，选择**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="6157e-137">In Visual Studio 2008, click **File**, select **Open**, and then click **Project/Solution**.</span></span>
    
6. <span data-ttu-id="6157e-138">浏览到保存该示例的位置，单击**mrxp32.vcproj**，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="6157e-138">Browse to the location where you saved the sample, click **mrxp32.vcproj**, and then click **Open**.</span></span>
    
7. <span data-ttu-id="6157e-139">在**生成**菜单上，单击**配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="6157e-139">On the **Build** menu, click **Configuration Manager**.</span></span>
    
8. <span data-ttu-id="6157e-140">**配置管理器**对话框中，转到**mrxp32**行中，和**配置**列中选择**版本**中，，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="6157e-140">In the **Configuration Manager** dialog box, go to the **mrxp32** row, and in the **Configuration** column select **Release**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="6157e-141">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="6157e-141">On the **Build** menu, click **Build Solution**.</span></span>
    
10. <span data-ttu-id="6157e-142">在**将文件另存为**对话框中，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="6157e-142">In the **Save File As** dialog box, click **Save**.</span></span>
    
11. <span data-ttu-id="6157e-143">在本示例保存的文件夹，右键单击安装批处理文件，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="6157e-143">In the folder where you saved the sample, right-click the installation batch file and click **Run as administrator**.</span></span>
    
12. <span data-ttu-id="6157e-144">在**用户帐户控制**对话框中，单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="6157e-144">In the **User Account Control** dialog box, click **Continue**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6157e-145">**install.bat**复制.dll 默认 Microsoft Office 安装文件夹，C:\Program Files\Microsoft Office\Office12\.</span><span class="sxs-lookup"><span data-stu-id="6157e-145">**install.bat** copies the .dll to the default Microsoft Office installation folder, C:\Program Files\Microsoft Office\Office12\.</span></span> <span data-ttu-id="6157e-146">如果您已在其他位置安装 Office 产品，右键单击**install.bat** ，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="6157e-146">If you have installed Office products in a different location, right-click **install.bat** and click **Edit**.</span></span> <span data-ttu-id="6157e-147">在记事本中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="6157e-147">The file opens in Notepad.</span></span> <span data-ttu-id="6157e-148">默认安装路径替换为您的计算机上使用的安装路径。</span><span class="sxs-lookup"><span data-stu-id="6157e-148">Replace the default installation path with the installation path used on your computer.</span></span> 
  
 <span data-ttu-id="6157e-149">**若要设置在 Outlook 中传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="6157e-149">**To set up the Transport Provider in Outlook**</span></span>
  
1. <span data-ttu-id="6157e-150">在 Outlook**工具**菜单上，单击**帐户设置**。</span><span class="sxs-lookup"><span data-stu-id="6157e-150">On the **Tools** menu of Outlook, click **Account Settings**.</span></span>
    
2. <span data-ttu-id="6157e-151">在**帐户设置**对话框的**电子邮件**选项卡中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="6157e-151">In the **Account Settings** dialog box, on the **Email** tab, click **New**.</span></span>
    
3. <span data-ttu-id="6157e-152">在**选择电子邮件服务**下单击**其他**，选择**MRXP 示例传输**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6157e-152">Under **Choose Email Service** click **Other**, select **MRXP Sample Transport**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="6157e-153">在**MRXP 传输配置**对话框中键入**用户的显示名称**。</span><span class="sxs-lookup"><span data-stu-id="6157e-153">In the **MRXP Transport Configuration** dialog box type a **User Display Name**.</span></span>
    
5. <span data-ttu-id="6157e-154">在**收件箱 （UNC 共享） 的路径**下输入的文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="6157e-154">Under **Path to Inbox (UNC Share)** enter a folder path.</span></span> <span data-ttu-id="6157e-155">也可以是到本地文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="6157e-155">This can also be a path to a local folder.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6157e-156">必须存在此路径。</span><span class="sxs-lookup"><span data-stu-id="6157e-156">This path must exist.</span></span> 
  
6. <span data-ttu-id="6157e-157">单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="6157e-157">Click **OK**.</span></span>
    
7. <span data-ttu-id="6157e-158">在**添加电子邮件帐户**对话框中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6157e-158">In the **Add Email Account** dialog box click **OK**.</span></span> <span data-ttu-id="6157e-159">单击**完成**，然后单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="6157e-159">Click **Finish** and then click **Close**.</span></span>
    
8. <span data-ttu-id="6157e-160">要开始使用 MRXP 帐户，请退出并重新启动 Outlook。</span><span class="sxs-lookup"><span data-stu-id="6157e-160">To start using the MRXP account, exit and restart Outlook.</span></span>
    
 <span data-ttu-id="6157e-161">**使用传输提供程序示例在 Outlook 中发送消息**</span><span class="sxs-lookup"><span data-stu-id="6157e-161">**To use the Transport Provider Sample to send a message in Outlook**</span></span>
  
1. <span data-ttu-id="6157e-162">在**文件**菜单中，单击**新建**，然后单击**邮件**。</span><span class="sxs-lookup"><span data-stu-id="6157e-162">On the **File** menu, click **New**, and then click **Mail Message**.</span></span>
    
2. <span data-ttu-id="6157e-163">在**到**框中键入的收件人使用的格式名称 **[MRXP:\<地址\>]**。</span><span class="sxs-lookup"><span data-stu-id="6157e-163">In the **To** box type the name of the recipient using the format **[MRXP:\<ADDRESS\>]**.</span></span> <span data-ttu-id="6157e-164">该地址是 UNC 共享或到收件人的收件箱的本地文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="6157e-164">The address is the UNC share or local folder path to the recipient's inbox.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6157e-165">如果有冒号或地址中的反斜杠，必须在每个冒号或反斜杠之前插入反斜杠。</span><span class="sxs-lookup"><span data-stu-id="6157e-165">If there are colons or backslashes in the address, you must insert a backslash before each colon or backslash.</span></span> <span data-ttu-id="6157e-166">例如，要发送到的邮件 [MRXP:C:\Mail\myDir] 必须键入`[MRXP:C\:\\Mail\\myDir]`。</span><span class="sxs-lookup"><span data-stu-id="6157e-166">For example, to send mail to [MRXP:C:\Mail\myDir] you must type  `[MRXP:C\:\\Mail\\myDir]`.</span></span> 
  
    > [!IMPORTANT]
    > <span data-ttu-id="6157e-167">收件人地址必须存在。</span><span class="sxs-lookup"><span data-stu-id="6157e-167">The recipient address must exist.</span></span> 
  
3. <span data-ttu-id="6157e-168">单击**帐户**，然后单击**MRXP 示例传输**。</span><span class="sxs-lookup"><span data-stu-id="6157e-168">Click **Account** and then click **MRXP Sample Transport**.</span></span>
    
4. <span data-ttu-id="6157e-169">键入消息，然后单击**发送**。</span><span class="sxs-lookup"><span data-stu-id="6157e-169">Type your message and click **Send**.</span></span> <span data-ttu-id="6157e-170">使用 MRXP 传输提供程序发送邮件。</span><span class="sxs-lookup"><span data-stu-id="6157e-170">The message is sent using the MRXP transport provider.</span></span>
    
 <span data-ttu-id="6157e-171">**要用于在 Outlook 中收到一条消息传输提供程序示例**</span><span class="sxs-lookup"><span data-stu-id="6157e-171">**To use the Transport Provider Sample to receive a message in Outlook**</span></span>
  
1. <span data-ttu-id="6157e-172">在**文件**菜单中，单击**新建**，然后单击**邮件**。</span><span class="sxs-lookup"><span data-stu-id="6157e-172">On the **File** menu, click **New**, and then click **Mail Message**.</span></span>
    
2. <span data-ttu-id="6157e-173">键入您的消息。</span><span class="sxs-lookup"><span data-stu-id="6157e-173">Type your message.</span></span>
    
3. <span data-ttu-id="6157e-174">单击**Microsoft Office 按钮**，单击**另存为**，然后单击**另存为**文件保存到您在安装过程中指定的收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="6157e-174">Click the **Microsoft Office Button**, click **Save As**, and then click **Save As** to save the file to the inbox folder you specified during setup.</span></span> 
    
4. <span data-ttu-id="6157e-175">在**另存为**对话框中，浏览到 UNC 共享或设置为您的收件箱的本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6157e-175">In the **Save As** dialog box, browse to the UNC share or local folder that you set as your inbox.</span></span> 
    
5. <span data-ttu-id="6157e-176">在**保存类型**下拉列表，单击**Outlook 邮件格式**。</span><span class="sxs-lookup"><span data-stu-id="6157e-176">In the **Save as type** drop down, click **Outlook Message Format**.</span></span>
    
6. <span data-ttu-id="6157e-177">键入文件的名称，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="6157e-177">Type a name for the file and click **Save**.</span></span>
    
7. <span data-ttu-id="6157e-178">将文件保存到共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="6157e-178">The file is saved to the shared folder.</span></span> <span data-ttu-id="6157e-179">MRXP 传输提供程序将邮件传递到 Outlook 中的收件箱。</span><span class="sxs-lookup"><span data-stu-id="6157e-179">The MRXP transport provider delivers the message to your Inbox in Outlook.</span></span>
    

