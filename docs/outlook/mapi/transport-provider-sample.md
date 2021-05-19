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
ms.openlocfilehash: def51a752abcb79a35980ed12eb73011c26d2597
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356586"
---
# <a name="transport-provider-sample"></a><span data-ttu-id="26bad-103">传输提供程序示例</span><span class="sxs-lookup"><span data-stu-id="26bad-103">Transport Provider Sample</span></span>

  
  
<span data-ttu-id="26bad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="26bad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="26bad-105">此示例使用文件和目录传输和接收消息。</span><span class="sxs-lookup"><span data-stu-id="26bad-105">This sample uses files and directories to transmit and receive messages.</span></span> <span data-ttu-id="26bad-106">它实现并注册一个非常简单的预处理器，它将一行文本附加到每个出站邮件。</span><span class="sxs-lookup"><span data-stu-id="26bad-106">It implements and registers a very simple preprocessor that appends a line of text to each outbound message.</span></span> <span data-ttu-id="26bad-107">该示例说明如何在传输中性封装格式与 TNEF 格式和文本 (拆分) 内容。</span><span class="sxs-lookup"><span data-stu-id="26bad-107">The sample illustrates how to split message content between Transport Neutral Encapsulation Format (TNEF) and text.</span></span> <span data-ttu-id="26bad-108">它还支持所有配置选项 (、向导以及编程配置) 和消息选项。</span><span class="sxs-lookup"><span data-stu-id="26bad-108">It also supports all configuration options (property sheets, wizards, and programmatic configuration) and message options.</span></span> <span data-ttu-id="26bad-109">它不支持远程传输接口。</span><span class="sxs-lookup"><span data-stu-id="26bad-109">It does not support the remote transport interfaces.</span></span> 
  
<span data-ttu-id="26bad-110">可以从 MAPI 代码示例[Outlook消息 API (下载) 示例](https://go.microsoft.com/fwlink/?LinkId=129740)。</span><span class="sxs-lookup"><span data-stu-id="26bad-110">You can download this sample from [Outlook Messaging API (MAPI) Code Samples](https://go.microsoft.com/fwlink/?LinkId=129740).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="26bad-111">可执行文件：</span><span class="sxs-lookup"><span data-stu-id="26bad-111">Executable:</span></span>  <br/> |<span data-ttu-id="26bad-112">mrxp32.dll</span><span class="sxs-lookup"><span data-stu-id="26bad-112">mrxp32.dll</span></span>  <br/> |
|<span data-ttu-id="26bad-113">源代码目录：</span><span class="sxs-lookup"><span data-stu-id="26bad-113">Source code directory:</span></span>  <br/> |<span data-ttu-id="26bad-114">SampleTransportProvider\MRXP</span><span class="sxs-lookup"><span data-stu-id="26bad-114">SampleTransportProvider\MRXP</span></span>  <br/> |
|<span data-ttu-id="26bad-115">语言：</span><span class="sxs-lookup"><span data-stu-id="26bad-115">Language:</span></span>  <br/> |<span data-ttu-id="26bad-116">C++</span><span class="sxs-lookup"><span data-stu-id="26bad-116">C++</span></span>  <br/> |
|<span data-ttu-id="26bad-117">平台：</span><span class="sxs-lookup"><span data-stu-id="26bad-117">Platforms:</span></span>  <br/> |<span data-ttu-id="26bad-118">Visual Studio 2008 年Windows Vista、Windows Server 2008、Windows XP SP2 和 Windows Server 2003 SP1 编译</span><span class="sxs-lookup"><span data-stu-id="26bad-118">Visual Studio 2008 to compile for Windows Vista, Windows Server 2008, Windows XP SP2, and Windows Server 2003 SP1</span></span>  <br/> |
   
## <a name="supported-features"></a><span data-ttu-id="26bad-119">支持的功能</span><span class="sxs-lookup"><span data-stu-id="26bad-119">Supported Features</span></span>

<span data-ttu-id="26bad-120">此示例支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="26bad-120">This sample supports the following features:</span></span>
  
- <span data-ttu-id="26bad-121">基本功能，如发送、接收和轮询新邮件。</span><span class="sxs-lookup"><span data-stu-id="26bad-121">Basic features such as sending, receiving, and polling for new messages.</span></span>
    
- <span data-ttu-id="26bad-122">交互式和编程配置。</span><span class="sxs-lookup"><span data-stu-id="26bad-122">Interactive and programmatic configuration.</span></span>
    
- <span data-ttu-id="26bad-123">**IMAPIStatus** 接口，属性设置除外。</span><span class="sxs-lookup"><span data-stu-id="26bad-123">The **IMAPIStatus** interface, except for property setting.</span></span> <span data-ttu-id="26bad-124">有关详细信息，请参阅 [IMAPIStatus ： IMAPIProp](imapistatusimapiprop.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="26bad-124">For more information, see the [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md) interface.</span></span> 
    
- <span data-ttu-id="26bad-125">线程安全。</span><span class="sxs-lookup"><span data-stu-id="26bad-125">Thread safety.</span></span>
    
- <span data-ttu-id="26bad-126">事件记录到文本文件。</span><span class="sxs-lookup"><span data-stu-id="26bad-126">Event logging to a text file.</span></span> <span data-ttu-id="26bad-127">文件自动限制为指定大小。</span><span class="sxs-lookup"><span data-stu-id="26bad-127">The file is automatically limited to a specified size.</span></span> <span data-ttu-id="26bad-128">所有传输会话都使用相同的文件。</span><span class="sxs-lookup"><span data-stu-id="26bad-128">All transport sessions use the same file.</span></span>
    
## <a name="unsupported-features"></a><span data-ttu-id="26bad-129">不受支持的功能</span><span class="sxs-lookup"><span data-stu-id="26bad-129">Unsupported Features</span></span>

<span data-ttu-id="26bad-130">此示例不支持对传入邮件进行异步检测。</span><span class="sxs-lookup"><span data-stu-id="26bad-130">This sample does not support asynchronous detection of incoming messages.</span></span>
  
 <span data-ttu-id="26bad-131">**安装示例传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="26bad-131">**To install the Sample Transport Provider**</span></span>
  
1. <span data-ttu-id="26bad-132">若要下载示例传输提供程序，请参阅下载Outlook [MAPI 示例](downloading-the-outlook-mapi-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="26bad-132">To download the Sample Transport Provider, see [Downloading the Outlook MAPI Samples](downloading-the-outlook-mapi-samples.md).</span></span>
    
2. <span data-ttu-id="26bad-133">找到保存 MAPI 示例Outlook文件夹。</span><span class="sxs-lookup"><span data-stu-id="26bad-133">Locate the folder where you saved the Outlook MAPI samples.</span></span> <span data-ttu-id="26bad-134">右键单击 **"OutlookMAPISamples- \< 版本号 \>** zip"文件夹，然后单击"**全部提取"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-134">Right-click the **OutlookMAPISamples-\<version number\>** zip folder and click **Extract All**.</span></span>
    
3. <span data-ttu-id="26bad-135">单击 **"** 浏览"，选择要保存示例的位置，然后单击"提取 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-135">Click **Browse**, select the location where you want to save the sample, and click **Extract**.</span></span>
    
4. <span data-ttu-id="26bad-136">运行 Visual Studio 2008。</span><span class="sxs-lookup"><span data-stu-id="26bad-136">Run Visual Studio 2008.</span></span>
    
5. <span data-ttu-id="26bad-137">在 Visual Studio 2008 中，单击"文件"，选择"打开 **"，然后单击"Project/解决方案"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-137">In Visual Studio 2008, click **File**, select **Open**, and then click **Project/Solution**.</span></span>
    
6. <span data-ttu-id="26bad-138">浏览到保存示例的位置，单击 **mrxp32.vcproj，** 然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-138">Browse to the location where you saved the sample, click **mrxp32.vcproj**, and then click **Open**.</span></span>
    
7. <span data-ttu-id="26bad-139">在"生成 **"菜单** 上，单击 **"配置管理器"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-139">On the **Build** menu, click **Configuration Manager**.</span></span>
    
8. <span data-ttu-id="26bad-140">在 **"配置管理器**"对话框中，转到 **"mrxp32"** 行，然后在"配置"列中选择"发布"，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-140">In the **Configuration Manager** dialog box, go to the **mrxp32** row, and in the **Configuration** column select **Release**, and then click **Close**.</span></span>
    
9. <span data-ttu-id="26bad-141">在"构建"菜单上，单击"构建解决方案"。</span><span class="sxs-lookup"><span data-stu-id="26bad-141">On the **Build** menu, click **Build Solution**.</span></span>
    
10. <span data-ttu-id="26bad-142">在"**将文件另存为**"对话框中，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-142">In the **Save File As** dialog box, click **Save**.</span></span>
    
11. <span data-ttu-id="26bad-143">在保存示例的文件夹中，右键单击安装批处理文件，然后单击"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-143">In the folder where you saved the sample, right-click the installation batch file and click **Run as administrator**.</span></span>
    
12. <span data-ttu-id="26bad-144">在“用户帐户控制”对话框中，单击“继续”。</span><span class="sxs-lookup"><span data-stu-id="26bad-144">In the **User Account Control** dialog box, click **Continue**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26bad-145">**install.bat** 将.dll复制到默认Microsoft Office文件夹 C：\Program Files\Microsoft Office\Office12\.</span><span class="sxs-lookup"><span data-stu-id="26bad-145">**install.bat** copies the .dll to the default Microsoft Office installation folder, C:\Program Files\Microsoft Office\Office12\.</span></span> <span data-ttu-id="26bad-146">If you have installed Office products in a different location， right-click **install.bat** and click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="26bad-146">If you have installed Office products in a different location, right-click **install.bat** and click **Edit**.</span></span> <span data-ttu-id="26bad-147">文件将在记事本。</span><span class="sxs-lookup"><span data-stu-id="26bad-147">The file opens in Notepad.</span></span> <span data-ttu-id="26bad-148">将默认安装路径替换为计算机上使用的安装路径。</span><span class="sxs-lookup"><span data-stu-id="26bad-148">Replace the default installation path with the installation path used on your computer.</span></span> 
  
 <span data-ttu-id="26bad-149">**在传输服务中设置传输Outlook**</span><span class="sxs-lookup"><span data-stu-id="26bad-149">**To set up the Transport Provider in Outlook**</span></span>
  
1. <span data-ttu-id="26bad-150">在"**工具"** 菜单上的Outlook，单击"**帐户设置"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-150">On the **Tools** menu of Outlook, click **Account Settings**.</span></span>
    
2. <span data-ttu-id="26bad-151">在"**帐户设置** 对话框中的"电子邮件 **"选项卡上**，单击"新建 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-151">In the **Account Settings** dialog box, on the **Email** tab, click **New**.</span></span>
    
3. <span data-ttu-id="26bad-152">在"**选择电子邮件服务**"下，单击"**其他"，** 选择 **"MRXP 示例传输**"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-152">Under **Choose Email Service** click **Other**, select **MRXP Sample Transport**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="26bad-153">在 **"MRXP 传输配置**"对话框中，键入 **"用户显示名称"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-153">In the **MRXP Transport Configuration** dialog box type a **User Display Name**.</span></span>
    
5. <span data-ttu-id="26bad-154">在 **"收件箱路径 (UNC 共享)** 输入文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="26bad-154">Under **Path to Inbox (UNC Share)** enter a folder path.</span></span> <span data-ttu-id="26bad-155">这还可以是本地文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="26bad-155">This can also be a path to a local folder.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="26bad-156">此路径必须存在。</span><span class="sxs-lookup"><span data-stu-id="26bad-156">This path must exist.</span></span> 
  
6. <span data-ttu-id="26bad-157">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="26bad-157">Click **OK**.</span></span>
    
7. <span data-ttu-id="26bad-158">在"**添加电子邮件帐户"对话框中**，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-158">In the **Add Email Account** dialog box click **OK**.</span></span> <span data-ttu-id="26bad-159">单击 **"完成**"，然后单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-159">Click **Finish** and then click **Close**.</span></span>
    
8. <span data-ttu-id="26bad-160">若要开始使用 MRXP 帐户，请退出并重新启动Outlook。</span><span class="sxs-lookup"><span data-stu-id="26bad-160">To start using the MRXP account, exit and restart Outlook.</span></span>
    
 <span data-ttu-id="26bad-161">**使用传输提供程序示例在传输中Outlook**</span><span class="sxs-lookup"><span data-stu-id="26bad-161">**To use the Transport Provider Sample to send a message in Outlook**</span></span>
  
1. <span data-ttu-id="26bad-162">在"**文件"** 菜单上，单击 **"新建**"，然后单击"**邮件"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-162">On the **File** menu, click **New**, and then click **Mail Message**.</span></span>
    
2. <span data-ttu-id="26bad-163">在 **"收件人** "框中，使用 **格式 [MRXP： ADDRESS ] 键入 \< \> 收件人的姓名**。</span><span class="sxs-lookup"><span data-stu-id="26bad-163">In the **To** box type the name of the recipient using the format **[MRXP:\<ADDRESS\>]**.</span></span> <span data-ttu-id="26bad-164">地址是收件人收件箱的 UNC 共享或本地文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="26bad-164">The address is the UNC share or local folder path to the recipient's inbox.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26bad-165">如果地址中存在冒号或反杠，则必须在每个冒号或反杠之前插入反杠。</span><span class="sxs-lookup"><span data-stu-id="26bad-165">If there are colons or backslashes in the address, you must insert a backslash before each colon or backslash.</span></span> <span data-ttu-id="26bad-166">例如，若要向 [MRXP：C：\Mail\myDir] 发送邮件，必须键入  `[MRXP:C\:\\Mail\\myDir]` 。</span><span class="sxs-lookup"><span data-stu-id="26bad-166">For example, to send mail to [MRXP:C:\Mail\myDir] you must type  `[MRXP:C\:\\Mail\\myDir]`.</span></span> 
  
    > [!IMPORTANT]
    > <span data-ttu-id="26bad-167">收件人地址必须存在。</span><span class="sxs-lookup"><span data-stu-id="26bad-167">The recipient address must exist.</span></span> 
  
3. <span data-ttu-id="26bad-168">单击 **帐户** ，然后单击 **MRXP 示例传输**。</span><span class="sxs-lookup"><span data-stu-id="26bad-168">Click **Account** and then click **MRXP Sample Transport**.</span></span>
    
4. <span data-ttu-id="26bad-169">键入邮件，然后单击"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-169">Type your message and click **Send**.</span></span> <span data-ttu-id="26bad-170">邮件使用 MRXP 传输提供程序发送。</span><span class="sxs-lookup"><span data-stu-id="26bad-170">The message is sent using the MRXP transport provider.</span></span>
    
 <span data-ttu-id="26bad-171">**使用传输提供程序示例在邮件中接收Outlook**</span><span class="sxs-lookup"><span data-stu-id="26bad-171">**To use the Transport Provider Sample to receive a message in Outlook**</span></span>
  
1. <span data-ttu-id="26bad-172">在"**文件"** 菜单上，单击 **"新建**"，然后单击"**邮件"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-172">On the **File** menu, click **New**, and then click **Mail Message**.</span></span>
    
2. <span data-ttu-id="26bad-173">键入邮件。</span><span class="sxs-lookup"><span data-stu-id="26bad-173">Type your message.</span></span>
    
3. <span data-ttu-id="26bad-174">单击 **"Microsoft Office按钮**"，单击"另存为"，然后单击"另存为"将文件保存到在设置期间指定的收件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="26bad-174">Click the **Microsoft Office Button**, click **Save As**, and then click **Save As** to save the file to the inbox folder you specified during setup.</span></span> 
    
4. <span data-ttu-id="26bad-175">在 **"另存为** "对话框中，浏览到您设置为收件箱的 UNC 共享或本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="26bad-175">In the **Save As** dialog box, browse to the UNC share or local folder that you set as your inbox.</span></span> 
    
5. <span data-ttu-id="26bad-176">在"**另存为类型"** 下拉列表中，单击 **"Outlook格式"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-176">In the **Save as type** drop down, click **Outlook Message Format**.</span></span>
    
6. <span data-ttu-id="26bad-177">键入文件的名称，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="26bad-177">Type a name for the file and click **Save**.</span></span>
    
7. <span data-ttu-id="26bad-178">文件保存到共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="26bad-178">The file is saved to the shared folder.</span></span> <span data-ttu-id="26bad-179">MRXP 传输提供程序将邮件发送到收件箱Outlook。</span><span class="sxs-lookup"><span data-stu-id="26bad-179">The MRXP transport provider delivers the message to your Inbox in Outlook.</span></span>
    

