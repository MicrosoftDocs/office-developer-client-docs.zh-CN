---
title: 与 Office 集成 IM 应用程序
manager: soliver
ms.date: 07/25/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: beba316b-1dfe-4e1b-adae-42418906c177
description: 本文介绍如何配置即时消息 (IM) 客户端应用程序，使其与 Office 2013，包括显示状态和发送即时消息从联系人卡片中的社会功能集成。
ms.openlocfilehash: 383aac24be347cf637d9e2f255623035eea8bc40
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779568"
---
# <a name="integrating-im-applications-with-office"></a><span data-ttu-id="bf973-103">与 Office 集成 IM 应用程序</span><span class="sxs-lookup"><span data-stu-id="bf973-103">Integrating IM applications with Office</span></span>

<span data-ttu-id="bf973-104">本文介绍如何配置即时消息 (IM) 客户端应用程序，使其与 Office 2013，包括显示状态和发送即时消息从联系人卡片中的社会功能集成。</span><span class="sxs-lookup"><span data-stu-id="bf973-104">This article describes how to configure an instant message (IM) client application so that it integrates with the social features in Office 2013, including displaying presence and sending instant messages from the contact card.</span></span>
  
<span data-ttu-id="bf973-105">如果您有任何问题或意见本技术文章或该描述的过程，您可以与 Microsoft 联系直接通过向[docthis@microsoft.com](mailto:docthis@microsoft.com)发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bf973-105">If you have any questions or comments about this technical article or the processes that it describes, you can contact Microsoft directly by sending an email to [docthis@microsoft.com](mailto:docthis@microsoft.com).</span></span>
  
## <a name="introduction"></a><span data-ttu-id="bf973-106">简介</span><span class="sxs-lookup"><span data-stu-id="bf973-106">Introduction</span></span>
<span data-ttu-id="bf973-107"><a name="off15_IMIntegration_Intro"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-107"></span></span>

<span data-ttu-id="bf973-108">Office 2013 提供了丰富集成 IM 客户端应用程序，包括 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="bf973-108">Office 2013 provides rich integration with IM client applications, including Lync 2013.</span></span> <span data-ttu-id="bf973-109">这种集成在 SharePoint 2013 页面上为用户提供从 Word 2013、 Excel 2013、 PowerPoint 2013、 Outlook 2013、 Visio 2013、 Project 2013 和 OneNote 2013 中的 IM 功能，以及提供状态集成。</span><span class="sxs-lookup"><span data-stu-id="bf973-109">This integration provides users with IM capabilities from within Word 2013, Excel 2013, PowerPoint 2013, Outlook 2013, Visio 2013, Project 2013, and OneNote 2013 as well as providing presence integration on SharePoint 2013 pages.</span></span> <span data-ttu-id="bf973-110">用户可以看到照片、 名称、 的状态，以及在其联系人列表中人员的联系人数据。</span><span class="sxs-lookup"><span data-stu-id="bf973-110">Users can see the photo, name, presence status, and contact data for people in their contacts list.</span></span> <span data-ttu-id="bf973-111">它们可以直接从联系人卡片 （某联系人信息和通信选项的 Office 2013 中的用户界面元素） 开始 IM 会话、 视频呼叫或电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="bf973-111">They can start an IM session, video call, or phone call directly from the contact card (the UI element in Office 2013 that surfaces contact information and communication options).</span></span> <span data-ttu-id="bf973-112">Office 2013 更加方便而不用您让您的电子邮件或文档之外保持连接到您的联系人。</span><span class="sxs-lookup"><span data-stu-id="bf973-112">Office 2013 makes it easy to stay connected to your contacts without taking you outside of your email or documents.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf973-113">本文使用术语 IM 客户端应用程序来明确引用将传达至 IM 服务的用户的计算机上安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf973-113">This article uses the term IM client application to refer specifically to the application installed on a user's computer that communicates to the IM service.</span></span> <span data-ttu-id="bf973-114">例如，Lync 2013 被视为 IM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf973-114">For example, Lync 2013 is considered an IM client application.</span></span> <span data-ttu-id="bf973-115">本文不提供有关如何 IM 客户端应用程序将传达至 IM 服务或 IM 服务本身详细信息。</span><span class="sxs-lookup"><span data-stu-id="bf973-115">This article does not provide details about how the IM client application communicates to the IM service or about the IM service itself.</span></span> 
  
<span data-ttu-id="bf973-116">可以自定义 IM 客户端应用程序，以便它使用 Office 进行通信。</span><span class="sxs-lookup"><span data-stu-id="bf973-116">You can customize an IM client application so that it communicates with Office.</span></span> <span data-ttu-id="bf973-117">具体而言，您可以修改 IM 应用程序，以使其显示在 Office ui 的以下信息：</span><span class="sxs-lookup"><span data-stu-id="bf973-117">Specifically, you can modify your IM application so that it displays the following information within the Office UI:</span></span>
  
- <span data-ttu-id="bf973-118">联系人的照片。</span><span class="sxs-lookup"><span data-stu-id="bf973-118">Contact photo.</span></span>
    
- <span data-ttu-id="bf973-119">联系人姓名。</span><span class="sxs-lookup"><span data-stu-id="bf973-119">Contact name.</span></span>
    
- <span data-ttu-id="bf973-120">联系人的个人状态注释。</span><span class="sxs-lookup"><span data-stu-id="bf973-120">Contact personal status note.</span></span>
    
- <span data-ttu-id="bf973-121">联系人状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-121">Contact presence status.</span></span>
    
- <span data-ttu-id="bf973-122">联系人可用性字符串 （例如，"有空"或"外出"）。</span><span class="sxs-lookup"><span data-stu-id="bf973-122">Contact availability string (for example, "Available" or "Out of Office").</span></span>
    
- <span data-ttu-id="bf973-123">联系人功能字符串 （例如，"视频就绪"）。</span><span class="sxs-lookup"><span data-stu-id="bf973-123">Contact capability string (for example, "Video Ready").</span></span>
    
- <span data-ttu-id="bf973-124">一次单击 IM 启动。</span><span class="sxs-lookup"><span data-stu-id="bf973-124">One-click IM launch.</span></span>
    
- <span data-ttu-id="bf973-125">一次单击视频呼叫启动。</span><span class="sxs-lookup"><span data-stu-id="bf973-125">One-click video call launch.</span></span>
    
- <span data-ttu-id="bf973-126">一键式电话呼叫启动 （包括 SIP、 电话号码、 语音邮件和呼叫新号码）。</span><span class="sxs-lookup"><span data-stu-id="bf973-126">One-click phone call launch (including SIP, phone number, voice mail, and call new number).</span></span>
    
- <span data-ttu-id="bf973-127">联系人管理 （将添加到 IM 组）。</span><span class="sxs-lookup"><span data-stu-id="bf973-127">Contact management (add to IM group).</span></span>
    
- <span data-ttu-id="bf973-128">联系人位置和时区。</span><span class="sxs-lookup"><span data-stu-id="bf973-128">Contact location and time zone.</span></span>
    
- <span data-ttu-id="bf973-129">联系人数据、 电话号码、 电子邮件地址、 标题和公司名称。</span><span class="sxs-lookup"><span data-stu-id="bf973-129">Contact data, phone number, email address, title, and company name.</span></span>
    
<span data-ttu-id="bf973-130">**图 1。Office 2013 中的联系人卡片**</span><span class="sxs-lookup"><span data-stu-id="bf973-130">**Figure 1. Contact card in Office 2013**</span></span>

<span data-ttu-id="bf973-131">![Office 2013 中的人员卡片](media/ocom15_peoplecard.png "Office 2013 中的人员卡片")</span><span class="sxs-lookup"><span data-stu-id="bf973-131">![The People Card in Office 2013](media/ocom15_peoplecard.png "The People Card in Office 2013")</span></span>
  
<span data-ttu-id="bf973-132">若要启用此与 Office 的集成，IM 客户端应用程序必须实现一组 Office 提供连接到它的接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-132">To enable this integration with Office, an IM client application must implement a set of interfaces that Office provides to connect to it.</span></span> <span data-ttu-id="bf973-133">这种集成的 Api 都包含在 Microsoft.Office.UC.dll 文件，其中包括 Lync 的版本的 Office 2013 安装中包含的[UCCollborationLib](http://msdn.microsoft.com/en-au/library/uccollaborationlib.aspx)命名空间 / for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="bf973-133">The APIs for this integration are included in the [UCCollborationLib](http://msdn.microsoft.com/en-au/library/uccollaborationlib.aspx) namespace that is contained in the Microsoft.Office.UC.dll file, which is installed with versions of Office 2013 that include Lync / Skype for Business.</span></span> <span data-ttu-id="bf973-134">**UCCollaborationLib**命名空间包含与 Office 集成时必须实现的接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-134">The **UCCollaborationLib** namespace includes the interfaces that you must implement to integrate with Office.</span></span> 
  
> [!IMPORTANT] 
> <span data-ttu-id="bf973-135">Lync 2013/Skype for Business 中嵌入所需的接口的类型库。</span><span class="sxs-lookup"><span data-stu-id="bf973-135">The type library for the required interfaces is embedded in Lync 2013/Skype for Business.</span></span> <span data-ttu-id="bf973-136">为第三方集成商它仅当在目标计算机上安装 Lync 2013 和 Skype for Business 时。</span><span class="sxs-lookup"><span data-stu-id="bf973-136">For third-party integrators, this works only when both Lync 2013 and Skype for Business are installed on the target machine.</span></span> <span data-ttu-id="bf973-137">如果要使用标准 Office 集成，您需要提取类型库在目标计算机上安装它。</span><span class="sxs-lookup"><span data-stu-id="bf973-137">If you are integrating using Office Standard, you need to extract the type library and install it on the target machine.</span></span> <span data-ttu-id="bf973-138">[Lync 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36824)包含 Microsoft.Office.UC.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="bf973-138">The [Lync 2013 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=36824) includes the Microsoft.Office.UC.dll file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="bf973-139">少量的 Office 2010 应用程序可以与第三方 IM 提供程序应用程序以类似方式集成： Outlook 2010、 Word 2010、 在 Excel 2010、 PowerPoint 2010 和 SharePoint Server 2010 （使用 ActiveX 控件）。</span><span class="sxs-lookup"><span data-stu-id="bf973-139">A handful of Office 2010 applications can integrate similarly with a third-party IM provider application: Outlook 2010, Word 2010, Excel 2010, PowerPoint 2010, and SharePoint Server 2010 (using an ActiveX control).</span></span> <span data-ttu-id="bf973-140">使用 Office 2013 的集成所需的步骤的许多也适用于 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="bf973-140">Many of the steps required for integration with Office 2013 apply to Office 2010 as well.</span></span> <span data-ttu-id="bf973-141">有多个 Office 2010 如何集成使用 IM 提供程序应用程序中的主要区别：</span><span class="sxs-lookup"><span data-stu-id="bf973-141">There are several key differences in how Office 2010 integrates with an IM provider application:</span></span> 
>  - <span data-ttu-id="bf973-142">Office 2010 不显示联系人的照片。</span><span class="sxs-lookup"><span data-stu-id="bf973-142">Office 2010 does not display the contact's photo.</span></span> 
>  - <span data-ttu-id="bf973-143">从 Office 2010 中，必须单独下载 Microsoft.Office.Uc.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="bf973-143">You must download the Microsoft.Office.Uc.dll file separately from Office 2010.</span></span> <span data-ttu-id="bf973-144">[Lync 2010 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=18898)包含用于 Office 2010 的 Microsoft.Office.UC.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="bf973-144">The [Lync 2010 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=18898) includes the Microsoft.Office.UC.dll file for Office 2010.</span></span> 
>  - <span data-ttu-id="bf973-145">当 Office 应用程序上的 IM 客户端应用程序调用[IUCOfficeIntegration.GetAuthenticationInfo](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)方法时，它将传递字符串"14.0.0.0"中。</span><span class="sxs-lookup"><span data-stu-id="bf973-145">When the Office application calls the [IUCOfficeIntegration.GetAuthenticationInfo](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) method on the IM client application, it passes in the string "14.0.0.0".</span></span> 
>  - <span data-ttu-id="bf973-146">Office 2010 枚举所有组和联系人，只要连接到 IM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf973-146">Office 2010 enumerates all groups and contacts as soon as it connects to an IM client application.</span></span> 
  
## <a name="how-office-integrates-with-an-im-client-application"></a><span data-ttu-id="bf973-147">Office 如何与 IM 客户端应用程序集成</span><span class="sxs-lookup"><span data-stu-id="bf973-147">How Office integrates with an IM client application</span></span>
<span data-ttu-id="bf973-148"><a name="off15_IMIntegration_How"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-148"></span></span>

<span data-ttu-id="bf973-149">Office 2013 应用程序启动时，它会通过下面的过程可以与默认 IM 客户端应用程序集成：</span><span class="sxs-lookup"><span data-stu-id="bf973-149">When an Office 2013 application starts, it goes through the following process to integrate with the default IM client application:</span></span>
  
1. <span data-ttu-id="bf973-150">它将检查注册表以发现默认 IM 客户端应用程序，然后连接到它。</span><span class="sxs-lookup"><span data-stu-id="bf973-150">It checks the registry to discover the default IM client application and then connects to it.</span></span>
    
2. <span data-ttu-id="bf973-151">它通过 IM 客户端应用程序的身份验证。</span><span class="sxs-lookup"><span data-stu-id="bf973-151">It authenticates with the IM client application.</span></span>
    
3. <span data-ttu-id="bf973-152">连接到特定由 IM 客户端应用程序公开的接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-152">It connects to specific interfaces that are exposed by the IM client application.</span></span>
    
4. <span data-ttu-id="bf973-153">它确定当前已登录的用户 （本地用户），包括获取用户的联系人，确定用户的状态，以及确定用户的 IM 功能 （即时消息、 视频聊天、 VOIP，等） 的功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-153">It determines the capabilities of the currently signed-in user (local user), including getting the user's contacts, determining the user's presence, and determining the user's IM capabilities (instant messaging, video chat, VOIP, and so on).</span></span>
    
5. <span data-ttu-id="bf973-154">它获取本地用户的联系人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="bf973-154">It gets presence information for the local user's contacts.</span></span>
    
6. <span data-ttu-id="bf973-155">IM 客户端应用程序关闭时，Office 2013 应用程序以无提示方式断开连接。</span><span class="sxs-lookup"><span data-stu-id="bf973-155">When the IM client application shuts down, the Office 2013 application silently disconnects.</span></span>
    
### <a name="discovering-the-im-application"></a><span data-ttu-id="bf973-156">发现 IM 应用程序</span><span class="sxs-lookup"><span data-stu-id="bf973-156">Discovering the IM application</span></span>

<span data-ttu-id="bf973-157">Office 应用程序查找多个特定的键和发现的默认 IM 客户端应用程序注册表中条目。</span><span class="sxs-lookup"><span data-stu-id="bf973-157">The Office application looks for several specific keys and entries in the registry to discover the default IM client application.</span></span> <span data-ttu-id="bf973-158">如果发现时的默认 IM 客户端应用程序，然后尝试连接到它。</span><span class="sxs-lookup"><span data-stu-id="bf973-158">If it discovers a default IM client application, it then attempts to connect to it.</span></span>
  
<span data-ttu-id="bf973-159">Office 应用程序经过发现默认 IM 客户端应用程序的过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf973-159">The process that the Office application goes through to discover the default IM client application is as follows:</span></span>
  
1. <span data-ttu-id="bf973-160">Office 应用程序查找要 HKEY_CURRENT_USER\Software\IM Providers\DefaultIMApp 将注册表子项中的是否已设置并读取应用程序名称列出。</span><span class="sxs-lookup"><span data-stu-id="bf973-160">The Office application looks to see if the HKEY_CURRENT_USER\Software\IM Providers\DefaultIMApp subkey in the registry is set and reads the application name listed there.</span></span>
    
2. <span data-ttu-id="bf973-161">Office 应用程序然后读取 HKEY_CURRENT_USER\Software\IM Providers\_应用程序名称_\UpAndRunning 密钥并监视更改的值。</span><span class="sxs-lookup"><span data-stu-id="bf973-161">The Office application then reads the HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning key and monitors the value for changes.</span></span>
    
3. <span data-ttu-id="bf973-162">接下来，Office 应用程序读取 HKEY_LOCAL_MACHINE\Software\IM Providers\_应用程序名称_注册表项，并获取那里存储的 ProcessName 和类 ID (CLSID) 值。</span><span class="sxs-lookup"><span data-stu-id="bf973-162">The Office application next reads the HKEY_LOCAL_MACHINE\Software\IM Providers\ _Application name_ registry key and gets the ProcessName and class ID (CLSID) values stored there.</span></span> 
    
4. <span data-ttu-id="bf973-163">IM 客户端应用程序已成功完成其开始序列并注册的所有正确的状态集成类后，将"2"的 HKEY_CURRENT_USER\Software\IM Providers\_应用程序名称_\UpAndRunning 关键指示客户端应用程序正在运行。</span><span class="sxs-lookup"><span data-stu-id="bf973-163">Once the IM client application has completed its start sequence successfully and registered all of the classes correctly for the presence integration, it sets the HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning key to "2", indicating that the client application is running.</span></span>
    
5. <span data-ttu-id="bf973-164">当 Office 应用程序发现 HKEY_CURRENT_USER\Software\IM Providers\_应用程序名称_\UpAndRunning 密钥已被设置为"2"时，它会检查 IM 客户端应用程序的过程名称的计算机上运行进程的列表。</span><span class="sxs-lookup"><span data-stu-id="bf973-164">When the Office application discovers that the HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning key has been set to "2", it checks the list of running processes on the computer for the process name of the IM client application.</span></span>
    
6. <span data-ttu-id="bf973-165">一旦在 Office 应用程序发现 IM 客户端应用程序使用的过程，Office 应用程序调用**CoCreateInstance**使用 CLSID 建立到为进程外 COM 服务器的 IM 客户端应用程序的连接。</span><span class="sxs-lookup"><span data-stu-id="bf973-165">Once the Office application finds the process that the IM client application uses, the Office application calls **CoCreateInstance** using the CLSID to establish a connection to the IM client application as an out-of-process COM server.</span></span> 
    
### <a name="authenticating-the-connection-to-the-im-application"></a><span data-ttu-id="bf973-166">身份验证与 IM 应用程序的连接</span><span class="sxs-lookup"><span data-stu-id="bf973-166">Authenticating the connection to the IM application</span></span>

<span data-ttu-id="bf973-167">Office 应用程序建立到 IM 客户端应用程序的连接后，它然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf973-167">After the Office application establishes a connection to the IM client application, it then does the following:</span></span>
  
1. <span data-ttu-id="bf973-168">Office 应用程序调用[IUnknown::QueryInterface](http://msdn.microsoft.com/zh-cn/library/ms682521%28v=VS.85%29.aspx)方法来检查[IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-168">The Office application calls [IUnknown::QueryInterface](http://msdn.microsoft.com/zh-cn/library/ms682521%28v=VS.85%29.aspx) method to check for the [IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) interface.</span></span> 
    
2. <span data-ttu-id="bf973-169">Office 应用程序然后调用**IUCOfficeIntegration.GetAuthenticationInfo**方法，传递中最高的支持的集成版本 (例如，"15.0.0.0")。</span><span class="sxs-lookup"><span data-stu-id="bf973-169">The Office application then calls the **IUCOfficeIntegration.GetAuthenticationInfo** method, passing in the highest supported integration version (for example, "15.0.0.0").</span></span> 
    
3. <span data-ttu-id="bf973-170">如果 IM 客户端应用程序支持的 Office 中作为参数传递的版本，应用程序将返回到调用代码的下面的硬编码 XML 字符串：</span><span class="sxs-lookup"><span data-stu-id="bf973-170">If the IM client application supports the version of Office passed in as a parameter, the application returns the following hard-coded XML string to the calling code:</span></span>
    
    `<authenticationinfo>`
    
   > [!NOTE]
   > <span data-ttu-id="bf973-171">出于旧版 IM 客户端应用程序必须返回的确切值`<authenticationinfo>`对**GetAuthenticationInfo**调用如果它所支持的版本 Office 中作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="bf973-171">For legacy reasons, the IM client application must return the exact value  `<authenticationinfo>` to the call to **GetAuthenticationInfo** if it supports the version of Office passed in as a parameter.</span></span> 
  
4. <span data-ttu-id="bf973-172">如果 IM 客户端应用程序未能返回一个值，Office 应用程序调用**GetAuthenticationInfo**再次具有最高支持下一版本的 Office (例如，"14.0.0.0")。</span><span class="sxs-lookup"><span data-stu-id="bf973-172">If the IM client application fails to return a value, the Office application calls the **GetAuthenticationInfo** method again with the next highest supported version of Office (for example, "14.0.0.0").</span></span> 
    
5. <span data-ttu-id="bf973-173">一旦 Office 确定 IM 客户端应用程序支持 IM 和状态集成，则它将连接到一所需的接口，若要完成初始化。</span><span class="sxs-lookup"><span data-stu-id="bf973-173">Once Office determines that the IM client application supports IM and presence integration, it connects to a required set of interfaces to finish initializing.</span></span> <span data-ttu-id="bf973-174">（有关详细信息，请参阅[Connecting to 所需的接口](#off15_IMIntegration_HowConnect)）。</span><span class="sxs-lookup"><span data-stu-id="bf973-174">(For more information, see [Connecting to required interfaces](#off15_IMIntegration_HowConnect).)</span></span>
    
<span data-ttu-id="bf973-175">如果 Office 应用程序遇到的上述步骤任何错误，它退出并重新在 Office 应用程序会话期间未建立状态集成。</span><span class="sxs-lookup"><span data-stu-id="bf973-175">If the Office application encounters an error on any of the steps above, it backs out and presence integration is not established again during the session of the Office application.</span></span> 
  
### <a name="connecting-to-required-interfaces"></a><span data-ttu-id="bf973-176">连接到所需的接口</span><span class="sxs-lookup"><span data-stu-id="bf973-176">Connecting to required interfaces</span></span>
<span data-ttu-id="bf973-177"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-177"></span></span>

<span data-ttu-id="bf973-178">身份验证后与 IM 客户端应用程序的连接，Office 应用程序尝试连接到一组 IM 客户端应用程序必须公开的所需的接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-178">After authenticating the connection to the IM client application, the Office application attempts to connect to a set of required interfaces that the IM client application must expose.</span></span> <span data-ttu-id="bf973-179">Office 应用程序可通过执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf973-179">The Office application accomplishes this by doing the following:</span></span>
  
- <span data-ttu-id="bf973-180">Office 应用程序获取[ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)对象通过调用**IUCOfficeIntegration.GetInterface**方法，并在**oiInterfaceLyncClient**传递常量[UCCollaborationLib.OIInterface](http://msdn.microsoft.com/library/UCCollaborationLib.OIInterface)枚举中。</span><span class="sxs-lookup"><span data-stu-id="bf973-180">The Office application gets an [ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) object by calling the **IUCOfficeIntegration.GetInterface** method, passing in the **oiInterfaceLyncClient** constant from the [UCCollaborationLib.OIInterface](http://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) enumeration.</span></span> 
    
- <span data-ttu-id="bf973-181">Office 应用程序获取[IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation)对象通过调用**IUCOfficeIntegration.GetInterface**方法，并在**oiInterfaceAutomation**传递常量**OIInterface**枚举中。</span><span class="sxs-lookup"><span data-stu-id="bf973-181">The Office application gets an [IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation) object by calling the **IUCOfficeIntegration.GetInterface** method, passing in the **oiInterfaceAutomation** constant from the **OIInterface** enumeration.</span></span> 
    
- <span data-ttu-id="bf973-182">Office 应用程序设置[_ILyncClientEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="bf973-182">The Office application sets up the [_ILyncClientEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) event listener.</span></span> 
    
- <span data-ttu-id="bf973-183">Office 应用程序设置[_IUCOfficeIntegrationEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="bf973-183">The Office application sets up the [_IUCOfficeIntegrationEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) event listener.</span></span> 
    
- <span data-ttu-id="bf973-184">Office 应用程序通过访问**ILyncClient.State**属性，从 IM 客户端应用程序中获取的登录状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-184">The Office application gets the sign-in state from the IM client application by accessing the **ILyncClient.State** property.</span></span> 
    
- <span data-ttu-id="bf973-185">Office 应用程序通过调用[UCCollaborationLib.OIFeature](http://msdn.microsoft.com/library/UCCollaborationLib.OIFeature)枚举中返回一个标志**IUCOfficeIntegration.GetSupportedFeatures**方法获取 IM 客户端应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-185">The Office application gets the capabilities of the IM client application by calling the **IUCOfficeIntegration.GetSupportedFeatures** method, which returns a flag from the [UCCollaborationLib.OIFeature](http://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) enumeration.</span></span> 
    
- <span data-ttu-id="bf973-186">Office 应用程序访问**ILyncClient.Self**属性来获取对[ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf)对象的引用。</span><span class="sxs-lookup"><span data-stu-id="bf973-186">The Office application accesses the **ILyncClient.Self** property to get a reference to an [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) object.</span></span> 
    
### <a name="retrieving-the-capabilities-of-the-local-user"></a><span data-ttu-id="bf973-187">检索本地用户的功能</span><span class="sxs-lookup"><span data-stu-id="bf973-187">Retrieving the capabilities of the local user</span></span>
<span data-ttu-id="bf973-188"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-188"></span></span>

<span data-ttu-id="bf973-189">Office 应用程序获取本地用户的功能，通过执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf973-189">The Office application gets the capabilities of the local user by doing the following:</span></span>
  
1. <span data-ttu-id="bf973-190">如果 IM 客户端应用程序支持**IClient2**接口，Office 将尝试通过访问**IClient2.PrivateContactManager**属性获取[IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager)对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-190">If the IM client application supports the **IClient2** interface, Office tries to get an [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) object by accessing the **IClient2.PrivateContactManager** property.</span></span> 
    
2. <span data-ttu-id="bf973-191">如果 IM 应用程序不支持**IClient2**接口，Office 应用程序通过访问**ILyncClient.ContactManager**属性获取**IContactManager**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-191">If the IM application does not support the **IClient2** interface, Office application gets an **IContactManager** object by accessing the **ILyncClient.ContactManager** property.</span></span> <span data-ttu-id="bf973-192">在建立任何其他即时消息功能前，IM 客户端应用程序必须成功返回**IContactManager**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-192">The IM client application must successfully return an **IContactManager** object before any other IM capabilities can be established.</span></span> 
    
3. <span data-ttu-id="bf973-193">Office 应用程序访问**ILyncClient.Uri**属性，然后调用**IContactManager.GetContactByUri**获取与本地用户关联的[IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact)对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-193">The Office application accesses the **ILyncClient.Uri** property and then calls **IContactManager.GetContactByUri** to get the [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) object associated with the local user.</span></span> 
    
4. <span data-ttu-id="bf973-194">Office 应用程序然后调用几个**IContact.CanStart**来建立**ModalityTypes.ucModalityInstantMessage**和**ModalityTypes.ucModalityAudioVideo**传入值的本地用户的功能连续。</span><span class="sxs-lookup"><span data-stu-id="bf973-194">The Office application then makes several calls to **IContact.CanStart** to establish the capabilities of the local user, passing in the values for **ModalityTypes.ucModalityInstantMessage** and **ModalityTypes.ucModalityAudioVideo** successively.</span></span> 
    
### <a name="retrieving-contact-presence"></a><span data-ttu-id="bf973-195">检索联系人的状态</span><span class="sxs-lookup"><span data-stu-id="bf973-195">Retrieving contact presence</span></span>
<span data-ttu-id="bf973-196"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-196"></span></span>

<span data-ttu-id="bf973-197">Office 应用程序获取联系人的状态，包括本地用户，通过执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bf973-197">The Office application gets contact presence, including the local user, by doing the following:</span></span> 
  
1. <span data-ttu-id="bf973-198">在 Office 应用程序调用**IContact.GetContactInformation**若要从联系人中获取的状态项。</span><span class="sxs-lookup"><span data-stu-id="bf973-198">The Office application calls **IContact.GetContactInformation** to get a presence item from the contact.</span></span> 
    
2. <span data-ttu-id="bf973-199">从联系人，然后在 Office 应用程序订阅更改状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-199">The Office application then subscribes to presence status changes from the contact.</span></span> <span data-ttu-id="bf973-200">它调用**IContactManager.CreateSubscription**获取[IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription)对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-200">It calls **IContactManager.CreateSubscription** to get an [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) object.</span></span> <span data-ttu-id="bf973-201">它然后调用**IContactSubscription.AddContact**将联系人添加到订阅，然后调用**IContactSubscription.Subscribe**以获取联系人的状态中的更改。</span><span class="sxs-lookup"><span data-stu-id="bf973-201">It then calls **IContactSubscription.AddContact** to add the contact to the subscription and then calls **IContactSubscription.Subscribe** to get changes in the contact's status.</span></span> 
    
3. <span data-ttu-id="bf973-202">如果 IM 应用程序支持**IContact2**，Office 将尝试通过调用**IContact2.BatchGetContactInformation2**获取状态信息。</span><span class="sxs-lookup"><span data-stu-id="bf973-202">If the IM application supports **IContact2**, Office attempts to get presence information by calling **IContact2.BatchGetContactInformation2**.</span></span>
    
4. <span data-ttu-id="bf973-203">Office 应用程序然后调用**IContact.BatchGetContactInformation**来检索该联系人的状态属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-203">The Office application then retrieves the presence properties for the contact by calling **IContact.BatchGetContactInformation**.</span></span> <span data-ttu-id="bf973-204">Office 应用程序可以通过访问**IContact.Settings**属性获取第二个一整套状态属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-204">The Office application can get a second set of presence properties by accessing the **IContact.Settings** property.</span></span> 
    
5. <span data-ttu-id="bf973-205">最后，Office 应用程序通过访问**IContact.CustomGroups**属性获取联系人的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="bf973-205">Finally, the Office application gets the contact's group membership by accessing the **IContact.CustomGroups** property.</span></span> <span data-ttu-id="bf973-206">这将返回一个[IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)集合，该集合包含的所有联系人都属于[IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-206">This returns an [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) collection that includes all of the [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) objects that the contact belongs to.</span></span> 
    
### <a name="disconnecting-from-the-im-application"></a><span data-ttu-id="bf973-207">断开 IM 应用程序</span><span class="sxs-lookup"><span data-stu-id="bf973-207">Disconnecting from the IM application</span></span>
<span data-ttu-id="bf973-208"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-208"></span></span>

<span data-ttu-id="bf973-209">当 Office 2013 应用程序检测到的来自 IM 应用程序的**OnShuttingDown**事件时，则它以无提示方式断开连接。</span><span class="sxs-lookup"><span data-stu-id="bf973-209">When the Office 2013 application detects the **OnShuttingDown** event from the IM application, it disconnects silently.</span></span> <span data-ttu-id="bf973-210">但是，如果在 Office 应用程序关闭前的 IM 应用程序时，Office 应用程序，不保证清理连接。</span><span class="sxs-lookup"><span data-stu-id="bf973-210">However, if the Office application shuts down before the IM application, the Office application does not guarantee that the connection is cleaned up.</span></span> <span data-ttu-id="bf973-211">IM 应用程序必须处理客户端连接泄漏。</span><span class="sxs-lookup"><span data-stu-id="bf973-211">The IM application must handle client connection leaks.</span></span> 
  
## <a name="setting-registry-keys-and-entries"></a><span data-ttu-id="bf973-212">设置注册表项和条目</span><span class="sxs-lookup"><span data-stu-id="bf973-212">Setting registry keys and entries</span></span>
<span data-ttu-id="bf973-213"><a name="off15_IMIntegration_SetRegistry"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-213"></span></span>

<span data-ttu-id="bf973-214">如前所述，支持 IM 的 Office 2013 应用程序查找特定键、 项和注册表来发现要连接到的 IM 客户端应用程序中的值。</span><span class="sxs-lookup"><span data-stu-id="bf973-214">As mentioned previously, the IM-capable Office 2013 applications look for specific keys, entries, and values in the registry to discover the IM client application to connect to.</span></span> <span data-ttu-id="bf973-215">这些注册表值提供 Office 应用程序的过程名称和充当 IM 客户端应用程序的对象模型 （实现**IUCOfficeIntegration**接口的类） 的入口点类的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="bf973-215">These registry values provide the Office application with the process name and CLSID of the class that acts as the entry point to the IM client application's object model (that is, the class that implements the **IUCOfficeIntegration** interface).</span></span> <span data-ttu-id="bf973-216">Office 应用程序共同创建的类，并为进程外 COM 服务器 IM 客户端应用程序中的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="bf973-216">The Office application co-creates that class and connects as a client to the out-of-process COM server in the IM client application.</span></span> 
  
<span data-ttu-id="bf973-217">表 1 用于标识键、 项和必须用注册表以与 Office 集成 IM 客户端应用程序编写的值。</span><span class="sxs-lookup"><span data-stu-id="bf973-217">Use Table 1 to identify the keys, entries, and values that must be written in the registry to integrate an IM client application with Office.</span></span>
  
<span data-ttu-id="bf973-218">**表 1。注册表项设置默认 IM 客户端应用程序**</span><span class="sxs-lookup"><span data-stu-id="bf973-218">**Table 1. Registry keys for setting the default IM client application**</span></span>

|<span data-ttu-id="bf973-219">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="bf973-219">**Key**</span></span>|<span data-ttu-id="bf973-220">**项**</span><span class="sxs-lookup"><span data-stu-id="bf973-220">**Entry**</span></span>|<span data-ttu-id="bf973-221">**类型**</span><span class="sxs-lookup"><span data-stu-id="bf973-221">**Type**</span></span>|<span data-ttu-id="bf973-222">**值**</span><span class="sxs-lookup"><span data-stu-id="bf973-222">**Value**</span></span>|<span data-ttu-id="bf973-223">**示例**</span><span class="sxs-lookup"><span data-stu-id="bf973-223">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf973-224">HKEY_LOCAL_MACHINE\Software\IM 提供程序\\< 应用程序名称\></span><span class="sxs-lookup"><span data-stu-id="bf973-224">HKEY_LOCAL_MACHINE\Software\IM Providers\\<Application name\></span></span>  <br/> |<span data-ttu-id="bf973-225">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="bf973-225">FriendlyName</span></span>  <br/> |<span data-ttu-id="bf973-226">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bf973-226">REG_SZ</span></span>  <br/> |<span data-ttu-id="bf973-227">第三方 IM 客户端应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="bf973-227">The name of the third-party IM client application.</span></span>  <br/> |<span data-ttu-id="bf973-228">Litware IM 2012</span><span class="sxs-lookup"><span data-stu-id="bf973-228">Litware IM 2012</span></span>  <br/> |
||<span data-ttu-id="bf973-229">ProcessName</span><span class="sxs-lookup"><span data-stu-id="bf973-229">ProcessName</span></span>  <br/> |<span data-ttu-id="bf973-230">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bf973-230">REG_SZ</span></span>  <br/> |<span data-ttu-id="bf973-231">第三方 IM 客户端应用程序的过程名称。</span><span class="sxs-lookup"><span data-stu-id="bf973-231">The process name of the third-party IM client application.</span></span>  <br/> |<span data-ttu-id="bf973-232">litware.exe</span><span class="sxs-lookup"><span data-stu-id="bf973-232">litware.exe</span></span>  <br/> |
||<span data-ttu-id="bf973-233">GUID</span><span class="sxs-lookup"><span data-stu-id="bf973-233">GUID</span></span>  <br/> |<span data-ttu-id="bf973-234">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bf973-234">REG_SZ</span></span>  <br/> |<span data-ttu-id="bf973-235">用于根目录中，IM 应用程序 （实现**IUCOfficeIntegration**接口的类） 中的 cocreatable 类的类 ID (CLSID)。</span><span class="sxs-lookup"><span data-stu-id="bf973-235">A class ID (CLSID) for the root, cocreatable class in the IM application (the class that implements the **IUCOfficeIntegration** interface).</span></span>  <br/> |<span data-ttu-id="bf973-236">(GUID)</span><span class="sxs-lookup"><span data-stu-id="bf973-236">(A GUID)</span></span>  <br/> |
|<span data-ttu-id="bf973-237">HKEY_CURRENT_USER\Software\IM 提供程序</span><span class="sxs-lookup"><span data-stu-id="bf973-237">HKEY_CURRENT_USER\Software\IM Providers</span></span>  <br/> |<span data-ttu-id="bf973-238">DefaultIMApp</span><span class="sxs-lookup"><span data-stu-id="bf973-238">DefaultIMApp</span></span>  <br/> |<span data-ttu-id="bf973-239">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="bf973-239">REG_SZ</span></span>  <br/> |<span data-ttu-id="bf973-240">IM 客户端应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="bf973-240">The name of the IM client application.</span></span> <span data-ttu-id="bf973-241">这必须是在 HKEY_LOCAL_MACHINE 中的顶级的注册表项 （配置单元） 的名称相同。</span><span class="sxs-lookup"><span data-stu-id="bf973-241">This must be the same as the name at the top-level registry key (hive) in the HKEY_LOCAL_MACHINE.</span></span>  <br/> |<span data-ttu-id="bf973-242">Litware</span><span class="sxs-lookup"><span data-stu-id="bf973-242">Litware</span></span>  <br/> |
|<span data-ttu-id="bf973-243">HKEY_CURRENT_USER\Software\IM 提供程序\\< 应用程序名称\></span><span class="sxs-lookup"><span data-stu-id="bf973-243">HKEY_CURRENT_USER\Software\IM Providers\\<Application name\></span></span>  <br/> |<span data-ttu-id="bf973-244">UpAndRunning</span><span class="sxs-lookup"><span data-stu-id="bf973-244">UpAndRunning</span></span>  <br/> |<span data-ttu-id="bf973-245">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="bf973-245">REG_DWORD</span></span>  <br/> | <span data-ttu-id="bf973-246">0 和 2 之间的整数值：</span><span class="sxs-lookup"><span data-stu-id="bf973-246">An integer value between 0 and 2:</span></span>  <br/>  <span data-ttu-id="bf973-247">0-不运行</span><span class="sxs-lookup"><span data-stu-id="bf973-247">0—Not running</span></span>  <br/>  <span data-ttu-id="bf973-248">1 — 启动</span><span class="sxs-lookup"><span data-stu-id="bf973-248">1—Starting</span></span>  <br/>  <span data-ttu-id="bf973-249">2 — 运行</span><span class="sxs-lookup"><span data-stu-id="bf973-249">2—Running</span></span>  <br/> <br/><span data-ttu-id="bf973-250">**注意**： 应用程序名称注册表项必须 DefaultIMApp 条目的值相同。</span><span class="sxs-lookup"><span data-stu-id="bf973-250">**NOTE**:  The application name registry key must be the same as the value of the DefaultIMApp entry.</span></span>           ||
   
## <a name="implementing-the-required-interfaces-for-integration-with-office"></a><span data-ttu-id="bf973-251">实现与 Office 集成所需的接口</span><span class="sxs-lookup"><span data-stu-id="bf973-251">Implementing the required interfaces for integration with Office</span></span>
<span data-ttu-id="bf973-252"><a name="off15_IMIntegration_ImplementRequired"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-252"></span></span>

<span data-ttu-id="bf973-253">有三个接口从 IM 客户端应用程序的可执行文件 （或 COM 服务器） 必须实现以便它可以与 Office 集成**UCCollaborationLib**命名空间。</span><span class="sxs-lookup"><span data-stu-id="bf973-253">There are three interfaces from the **UCCollaborationLib** namespace that the executable (or COM server) of an IM client application must implement so that it can integrate with Office.</span></span> <span data-ttu-id="bf973-254">如果未实现这些接口，Office 应用程序在初始化过程中退出和未建立与 IM 客户端应用程序的连接。</span><span class="sxs-lookup"><span data-stu-id="bf973-254">If these interfaces are not implemented, the Office application backs out during the initialization process and the connection with the IM client application is not established.</span></span> 
  
<span data-ttu-id="bf973-255">所需的接口，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf973-255">The required interfaces are as follows:</span></span>
  
- <span data-ttu-id="bf973-256">[IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)— 虽然不要求，在 **_IUCOfficeIntegrationEvents**接口，还应在相同的派生类中实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-256">[IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)—Although not required, the **_IUCOfficeIntegrationEvents** interface should also be implemented in the same derived class.</span></span> 
    
- <span data-ttu-id="bf973-257">[ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)— 虽然不要求，在 **_ILyncClientEvents**接口，还应在相同的派生类中实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-257">[ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)—Although not required, the **_ILyncClientEvents** interface should also be implemented in the same derived class.</span></span> 
    
- [<span data-ttu-id="bf973-258">IAutomation</span><span class="sxs-lookup"><span data-stu-id="bf973-258">IAutomation</span></span>](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation)
    
### <a name="iucofficeintegration-interface"></a><span data-ttu-id="bf973-259">IUCOfficeIntegration 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-259">IUCOfficeIntegration interface</span></span>
<span data-ttu-id="bf973-260"><a name="off15_IMIntegration_ImplementRequired_IUCOfficeIntegration"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-260"></span></span>

<span data-ttu-id="bf973-261">**IUCOfficeIntegration**接口提供了 Office 应用程序连接到 IM 客户端应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="bf973-261">The **IUCOfficeIntegration** interface provides the entry-point for an Office application to connect to the IM client application.</span></span> <span data-ttu-id="bf973-262">该接口定义的启动与 IM 客户端应用程序的连接过程的一部分调用 Office 应用程序的三种方法。</span><span class="sxs-lookup"><span data-stu-id="bf973-262">The interface defines three methods that an Office application calls as part of the process of initiating a connection with the IM client application.</span></span> <span data-ttu-id="bf973-263">必须共同可创建实现**IUCOfficeIntegration**接口的类，以便 Office 可以共同创建它的一个实例。</span><span class="sxs-lookup"><span data-stu-id="bf973-263">The class that implements the **IUCOfficeIntegration** interface must be co-creatable so that Office can co-create an instance of it.</span></span> <span data-ttu-id="bf973-264">此外，它必须公开 HKEY_LOCAL_MACHINE\Software\IM Providers\_应用程序名称_注册表项中的 GUID 项输入值的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="bf973-264">In addition, it must expose the CLSID that is entered as the value for the GUID entry in the HKEY_LOCAL_MACHINE\Software\IM Providers\  _Application name_ registry key.</span></span> 
  
<span data-ttu-id="bf973-265">继承自**IUCOfficeIntegration**类还应实现 **_IUCOfficeIntegrationEvents**接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-265">The class that inherits from **IUCOfficeIntegration** should also implement the **_IUCOfficeIntegrationEvents** interface.</span></span> <span data-ttu-id="bf973-266">**_IUCOfficeIntegrationEvents**接口包含公开**IUCOfficeIntegration**接口的事件处理程序的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-266">The **_IUCOfficeIntegrationEvents** interface contains the members that expose the event handlers of the **IUCOfficeIntegration** interface.</span></span> 
  
<span data-ttu-id="bf973-267">表 2 显示了必须继承自**IUCOfficeIntegration**和 **_IUCOfficeIntegration**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-267">Table 2 shows the members that must be implemented in the class that inherits from **IUCOfficeIntegration** and **_IUCOfficeIntegration**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-268">有关**IUCOfficeIntegration** **_IUCOfficeIntegrationEvents**接口和其成员的详细信息，请参阅[UCCollaborationLib.IUCOfficeIntegration](http://msdn.microsoft.com/library/UCCollaborationLib.IUCOfficeIntegration)和[UCCollaborationLib._IUCOfficeIntegrationEvents](http://msdn.microsoft.com/library/UCCollaborationLib._IUCOfficeIntegrationEvents).</span><span class="sxs-lookup"><span data-stu-id="bf973-268">For more information about the **IUCOfficeIntegration** and **_IUCOfficeIntegrationEvents** interfaces and their members, see [UCCollaborationLib.IUCOfficeIntegration](http://msdn.microsoft.com/library/UCCollaborationLib.IUCOfficeIntegration) and [UCCollaborationLib._IUCOfficeIntegrationEvents](http://msdn.microsoft.com/library/UCCollaborationLib._IUCOfficeIntegrationEvents).</span></span> 
  
<span data-ttu-id="bf973-269">**表 2。IUCOfficeIntegration 和 _IUCOfficeIntegrationEvents 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-269">**Table 2. Implementation of the IUCOfficeIntegration and _IUCOfficeIntegrationEvents interfaces**</span></span>

|<span data-ttu-id="bf973-270">**接口**</span><span class="sxs-lookup"><span data-stu-id="bf973-270">**Interface**</span></span>|<span data-ttu-id="bf973-271">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-271">**Member**</span></span>|<span data-ttu-id="bf973-272">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-272">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf973-273">**IUCOfficeIntegration**</span><span class="sxs-lookup"><span data-stu-id="bf973-273">**IUCOfficeIntegration**</span></span> <br/> |<span data-ttu-id="bf973-274">**GetAuthenticationInfo**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-274">**GetAuthenticationInfo** method</span></span>  <br/> |<span data-ttu-id="bf973-275">获取身份验证信息字符串。</span><span class="sxs-lookup"><span data-stu-id="bf973-275">Gets the authentication info string.</span></span>  <br/> |
||<span data-ttu-id="bf973-276">**GetInterface**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-276">**GetInterface** method</span></span>  <br/> |<span data-ttu-id="bf973-277">获取特定版本的接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-277">Gets the interface of a particular version.</span></span>  <br/> |
||<span data-ttu-id="bf973-278">**GetSupportedFeatures**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-278">**GetSupportedFeatures** method</span></span>  <br/> |<span data-ttu-id="bf973-279">获取的受支持的 Office 集成功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-279">Gets the supported Office integration features.</span></span>  <br/> |
|<span data-ttu-id="bf973-280">**_IUCOfficeIntegrationEvents**</span><span class="sxs-lookup"><span data-stu-id="bf973-280">**_IUCOfficeIntegrationEvents**</span></span> <br/> |<span data-ttu-id="bf973-281">**OnShuttingDown**事件</span><span class="sxs-lookup"><span data-stu-id="bf973-281">**OnShuttingDown** event</span></span>  <br/> |<span data-ttu-id="bf973-282">IM 客户端应用程序尝试关闭时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="bf973-282">The event raised when the IM client application is trying to shut down.</span></span>  <br/> |
   
<span data-ttu-id="bf973-283">使用以下代码定义继承 IM 客户端应用程序中的**IUCOfficeIntegration**和 **_IUCOfficeIntegration**接口的类。</span><span class="sxs-lookup"><span data-stu-id="bf973-283">Use the following code to define a class that inherits from the **IUCOfficeIntegration** and **_IUCOfficeIntegration** interfaces within an IM client application.</span></span> 
  
```cs
// An example of a class that can be co-created and can integrate
// with Office as an IM provider.
[ClassInterface(ClassInterfaceType.None)]
[ComSourceInterfaces(typeof(_IUCOfficeIntegrationEvents))]
[Guid("{CLSID value}"), ComVisible(true)]
public class LitwareClientAppObject : IUCOfficeIntegration
{
    // Implementation details omitted.
}

```

<span data-ttu-id="bf973-284">**GetAuthenticationInfo**方法采用作为_版本_参数的参数字符串。</span><span class="sxs-lookup"><span data-stu-id="bf973-284">The **GetAuthenticationInfo** method takes a string as an argument for the  _version_ parameter.</span></span> <span data-ttu-id="bf973-285">Office 应用程序调用此方法时，它将传递两个字符串之一的参数，具体取决于 Office 的版本。</span><span class="sxs-lookup"><span data-stu-id="bf973-285">When the Office application calls this method, it passes in one of two strings for the argument, depending on the version of Office.</span></span> <span data-ttu-id="bf973-286">Office 应用程序时提供的 IM 客户端应用程序支持的 Office 版本的方法 （即，支持功能） 的**GetAuthenticationInfo**方法返回一个硬编码的 XML 字符串`<authenticationinfo>`。</span><span class="sxs-lookup"><span data-stu-id="bf973-286">When the Office application supplies the method with the version of Office that the IM client application supports (that is, supports the functionality), the **GetAuthenticationInfo** method returns a hard-coded XML string `<authenticationinfo>`.</span></span> 
  
<span data-ttu-id="bf973-287">使用以下代码实现 IM 客户端应用程序代码中的**GetAuthentication**方法。</span><span class="sxs-lookup"><span data-stu-id="bf973-287">Use the following code to implement the **GetAuthentication** method within the IM client application code.</span></span> 
  
```cs
public string GetAuthenticationInfo(string _version)
{
    // Define the version of Office that the IM client application supports.
    string supportedOfficeVersion = "15.0.0.0";
    // Do a simple check for equivalency.
    if (supportedOfficeVersion == _version)
    {
        // If the version of Office is supported, this method must 
        // return the string literal "<authenticationinfo>" exactly.
        return "<authenticationinfo>";
    }
    else
    {
        return null;
    }
}

```

<span data-ttu-id="bf973-288">**GetInterface**方法调用的代码中，具体取决于什么作为的_界面_参数作为参数传入到 shuttles 类的引用。</span><span class="sxs-lookup"><span data-stu-id="bf973-288">The **GetInterface** method shuttles references to classes to the calling code, depending on what is passed in as an argument for the  _interface_ parameter.</span></span> <span data-ttu-id="bf973-289">Office 应用程序调用**GetInterface**方法时，它中传递两个值之一接口参数： **oiInterfaceILyncClient**常量 （1） 或 （2） 的[**oiInterfaceIAutomation**常量UCCollaborationLib.OIInterface](http://msdn.microsoft.com/library/UCCollaborationLib.OIInterface)枚举。</span><span class="sxs-lookup"><span data-stu-id="bf973-289">When an Office application calls the **GetInterface** method, it passes in one of two values for the interface parameter: either the **oiInterfaceILyncClient** constant (1) or the **oiInterfaceIAutomation** constant (2) of the [UCCollaborationLib.OIInterface](http://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) enumeration.</span></span> <span data-ttu-id="bf973-290">如果在 Office 应用程序通过**oiInterfaceILyncClient**常量， **GetInterface**方法将返回对实现**ILyncClient**接口的类的引用。</span><span class="sxs-lookup"><span data-stu-id="bf973-290">If the Office application passes in the **oiInterfaceILyncClient** constant, the **GetInterface** method returns a reference to a class that implements the **ILyncClient** interface.</span></span> <span data-ttu-id="bf973-291">如果在 Office 应用程序通过**oiInterfaceIAutomation**常量，该**GetInterface**方法将返回实现**IAutomation**接口的类。</span><span class="sxs-lookup"><span data-stu-id="bf973-291">If the Office application passes in the **oiInterfaceIAutomation** constant, the **GetInterface** method returns a class that implements the **IAutomation** interface.</span></span> 
  
<span data-ttu-id="bf973-292">使用下面的代码示例来实现 IM 客户端应用程序代码中的**GetInterface**方法。</span><span class="sxs-lookup"><span data-stu-id="bf973-292">Use the following code example to implement the **GetInterface** method within the IM client application code.</span></span> 
  
```cs
public object GetInterface(string _version, OIInterface _interface)
{
    // These objects implement the ILyncClient or IAutomation 
    // interfaces respectively. There is no restriction on what these
    // classes are named.
    IMClient imClient = new IMClient();
    IMClientAutomation imAutomation = new IMClientAutomation();
    // Return different object references depending on the value passed in
    // for the _interface parameter.
    switch (_interface)
    {
        // The calling code is asking for an object that inherits
        // from ILyncClient, so it returns such an object.
        case OIInterface.oiInterfaceILyncClient:
        {
            return imClient;
        }
        // The calling code is asking for an object that inherits
        // from IAutomation, so it returns such an object.
        case OIInterface.oiInterfaceIAutomation:
        {
            return imAutomation;
        }
        default:
        {
            throw new NotImplementedException();
        }
    }
}

```

<span data-ttu-id="bf973-293">**GetSupportedFeatures**方法返回有关 IM 客户端应用程序支持的 IM 功能的信息。</span><span class="sxs-lookup"><span data-stu-id="bf973-293">The **GetSupportedFeatures** method returns information about the IM features that the IM client application supports.</span></span> <span data-ttu-id="bf973-294">计其唯一参数，_版本_的字符串。</span><span class="sxs-lookup"><span data-stu-id="bf973-294">It takes a string for its only parameter,  _version_.</span></span> <span data-ttu-id="bf973-295">Office 应用程序调用**GetSupportFeatures**方法时，该方法将返回[UCCollaborationLib.OIFeature](http://msdn.microsoft.com/library/UCCollaborationLib.OIFeature)枚举中的一个值。</span><span class="sxs-lookup"><span data-stu-id="bf973-295">When the Office application calls the **GetSupportFeatures** method, the method returns a value from the [UCCollaborationLib.OIFeature](http://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) enumeration.</span></span> <span data-ttu-id="bf973-296">返回的值指定的 IM 客户端应用程序的每个功能对 Office 应用程序指示通过将一个标志添加到值的 IM 客户端的功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-296">The returned value specifies the capabilities of the IM client, where each capability of the IM client application is indicated to the Office application by adding a flag to the value.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="bf973-297">Office 2013 应用程序忽略**OIFeature**枚举中的以下常量：</span><span class="sxs-lookup"><span data-stu-id="bf973-297">Office 2013 applications ignore the following constants in the **OIFeature** enumeration:</span></span> 
> - <span data-ttu-id="bf973-298">**oiFeaturePictures**(2)</span><span class="sxs-lookup"><span data-stu-id="bf973-298">**oiFeaturePictures** (2)</span></span> 
> - <span data-ttu-id="bf973-299">**oiFeatureFreeBusyIntegration**</span><span class="sxs-lookup"><span data-stu-id="bf973-299">**oiFeatureFreeBusyIntegration**</span></span>
> - <span data-ttu-id="bf973-300">**oiFeaturePhoneNormalization**</span><span class="sxs-lookup"><span data-stu-id="bf973-300">**oiFeaturePhoneNormalization**</span></span>
  
<span data-ttu-id="bf973-301">使用下面的代码示例来实现 IM 客户端应用程序代码中的**GetSupportFeatures**方法。</span><span class="sxs-lookup"><span data-stu-id="bf973-301">Use the following code example to implement the **GetSupportFeatures** method within the IM client application code.</span></span> 
  
```cs
public OIFeature GetSupportedFeatures(string _version)
{
    OIFeature supportedFeature1 = OIFeature.oiFeatureQuickContacts;
    OIFeature supportedFeature2 = OIFeature.oiFeatureFastSearch;
    return (supportedFeature1 | supportedFeature2);
}

```

### <a name="ilyncclient-interface"></a><span data-ttu-id="bf973-302">ILyncClient 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-302">ILyncClient interface</span></span>
<span data-ttu-id="bf973-303"><a name="off15_IMIntegration_ImplementRequired_ILyncClient"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-303"></span></span>

<span data-ttu-id="bf973-304">**ILyncClient**接口将映射到在即时消息客户端应用程序自身的功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-304">The **ILyncClient** interface maps to the capabilities of the IM client application itself.</span></span> <span data-ttu-id="bf973-305">它公开本地用户和其他几个设置登录到的应用程序 （本地用户，由[UCCollaborationLib.ISelf](http://msdn.microsoft.com/library/UCCollaborationLib.ISelf)接口） 的应用程序的状态、 联系人列表中的人员所引用的属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-305">It exposes properties that refer to the person who is signed into the application (the local user, represented by the [UCCollaborationLib.ISelf](http://msdn.microsoft.com/library/UCCollaborationLib.ISelf) interface), the state of the application, the list of contacts for the local user, and several other settings.</span></span> <span data-ttu-id="bf973-306">时正在尝试连接到 IM 客户端应用程序，Office 应用程序获取对实现**ILyncClient**接口的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="bf973-306">When it's trying to connect to the IM client application, the Office application gets a reference to an object that implements the **ILyncClient** interface.</span></span> <span data-ttu-id="bf973-307">从该参考中，可以访问 Office 何种 IM 客户端应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-307">From that reference, Office can access much of the functionality of the IM client application.</span></span> 
  
<span data-ttu-id="bf973-308">此外，实现**ILyncClient**接口的类还应实现 **_ILyncClientEvents**接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-308">In addition, the class that implements the **ILyncClient** interface should also implement the **_ILyncClientEvents** interface.</span></span> <span data-ttu-id="bf973-309">**_ILyncClientEvents**接口将公开几个所需的监控 IM 客户端应用程序的状态的事件。</span><span class="sxs-lookup"><span data-stu-id="bf973-309">The **_ILyncClientEvents** interface exposes several of the events that are required for monitoring the state of the IM client application.</span></span> 
  
<span data-ttu-id="bf973-310">表 3 显示了必须继承自**ILyncClient**和 **_ILyncClientEvents**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-310">Table 3 shows the members that must be implemented in the class that inherits from **ILyncClient** and **_ILyncClientEvents**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-311">**ILyncClient**的任何成员或**\_ILyncClientEvents**表中未列出的接口必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-311">Any member of the **ILyncClient** or **\_ILyncClientEvents** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-312">已存在，但未实现的成员可以引发**NotImplementedException**或**E\_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-312">Members that are present but not implemented can throw a **NotImplementedException** or **E\_NOTIMPL** error.</span></span> 
> 
> <span data-ttu-id="bf973-313">有关**ILyncClient** **_ILyncClientEvents**接口和其成员的详细信息，请参阅[UCCollaborationLib.ILyncClient](http://msdn.microsoft.com/library/UCCollaborationLib.ILyncClient)和[UCCollaborationLib._ILyncClientEvents](http://msdn.microsoft.com/library/UCCollaborationLib._ILyncClientEvents)。</span><span class="sxs-lookup"><span data-stu-id="bf973-313">For more information about the **ILyncClient** and **_ILyncClientEvents** interfaces and their members, see [UCCollaborationLib.ILyncClient](http://msdn.microsoft.com/library/UCCollaborationLib.ILyncClient) and [UCCollaborationLib._ILyncClientEvents](http://msdn.microsoft.com/library/UCCollaborationLib._ILyncClientEvents).</span></span> 
  
<span data-ttu-id="bf973-314">**表 3。ILyncClient 和 ILyncClientEvents 接口实现。**</span><span class="sxs-lookup"><span data-stu-id="bf973-314">**Table 3. Implementation of ILyncClient and ILyncClientEvents interfaces**</span></span>

|<span data-ttu-id="bf973-315">**接口**</span><span class="sxs-lookup"><span data-stu-id="bf973-315">**Interface**</span></span>|<span data-ttu-id="bf973-316">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-316">**Member**</span></span>|<span data-ttu-id="bf973-317">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-317">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf973-318">**ILyncClient**</span><span class="sxs-lookup"><span data-stu-id="bf973-318">**ILyncClient**</span></span> <br/> |<span data-ttu-id="bf973-319">**ContactManager**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-319">**ContactManager** property</span></span>  <br/> |<span data-ttu-id="bf973-320">获取联系人组管理器。</span><span class="sxs-lookup"><span data-stu-id="bf973-320">Gets the contact group manager.</span></span>  <br/> |
||<span data-ttu-id="bf973-321">**ConversationManager**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-321">**ConversationManager** property</span></span>  <br/> |<span data-ttu-id="bf973-322">获取对话管理器。</span><span class="sxs-lookup"><span data-stu-id="bf973-322">Gets the conversations manager.</span></span>  <br/> |
||<span data-ttu-id="bf973-323">**自我**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-323">**Self** property</span></span>  <br/> |<span data-ttu-id="bf973-324">获取的**自我**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-324">Gets the **Self** object.</span></span>  <br/> |
||<span data-ttu-id="bf973-325">**登录**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-325">**SignIn** method</span></span>  <br/> |<span data-ttu-id="bf973-326">启动 IM 客户端应用程序登录过程具有特定的可用性。</span><span class="sxs-lookup"><span data-stu-id="bf973-326">Starts the IM client application sign-in process with a specific availability.</span></span>  <br/> |
||<span data-ttu-id="bf973-327">**State**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-327">**State** property</span></span>  <br/> |<span data-ttu-id="bf973-328">获取当前平台状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-328">Gets the current platform state.</span></span>  <br/> |
||<span data-ttu-id="bf973-329">**Uri** 属性</span><span class="sxs-lookup"><span data-stu-id="bf973-329">**Uri** property</span></span>  <br/> |<span data-ttu-id="bf973-330">获取 IM 客户端应用程序的 URI。</span><span class="sxs-lookup"><span data-stu-id="bf973-330">Gets the URI of the IM client application.</span></span>  <br/> |
|<span data-ttu-id="bf973-331">**_ILyncClientEvents**</span><span class="sxs-lookup"><span data-stu-id="bf973-331">**_ILyncClientEvents**</span></span> <br/> |<span data-ttu-id="bf973-332">**OnStateChanged**事件</span><span class="sxs-lookup"><span data-stu-id="bf973-332">**OnStateChanged** event</span></span>  <br/> |<span data-ttu-id="bf973-333">IM 客户端应用程序状态更改时引发。</span><span class="sxs-lookup"><span data-stu-id="bf973-333">Raised when the IM client application state changes.</span></span> <span data-ttu-id="bf973-334">您应处理此事件，并获取**eventData.NewState**属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-334">You should handle this event and get the **eventData.NewState** property.</span></span> <span data-ttu-id="bf973-335">当应用程序中的任何子系统导致状态更改时，绑定到 IM 客户端应用程序实例的所有进程引发该事件。</span><span class="sxs-lookup"><span data-stu-id="bf973-335">The event is raised for all processes bound to an instance of an IM client application when any subsystem in the application causes the state change.</span></span>  <br/> |
   
<span data-ttu-id="bf973-336">在初始化过程中，Office 访问**ILyncClient.State**属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-336">During the initialization process, Office accesses the **ILyncClient.State** property.</span></span> <span data-ttu-id="bf973-337">此属性需要从[UCCollaborationLib.ClientState](http://msdn.microsoft.com/library/UCCollaborationLib.ClientState)枚举返回一个值。</span><span class="sxs-lookup"><span data-stu-id="bf973-337">This property needs to return a value from the [UCCollaborationLib.ClientState](http://msdn.microsoft.com/library/UCCollaborationLib.ClientState) enumeration.</span></span> 
  
```cs
private ClientState _clientState;
public ClientState State
{
    get
    {
        return this._clientState;
    }
}

```

<span data-ttu-id="bf973-338">**State**属性存储 IM 客户端应用程序的当前状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-338">The **State** property stores the current status of the IM client application.</span></span> <span data-ttu-id="bf973-339">必须设置并更新整个 IM 客户端应用程序会话。</span><span class="sxs-lookup"><span data-stu-id="bf973-339">It must be set and updated throughout the IM client application session.</span></span> <span data-ttu-id="bf973-340">当 IM 客户端应用程序登录，则注销，或关闭时，应设置的**状态**属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-340">When the IM client application signs in, signs out, or shuts down, it should set the **State** property.</span></span> <span data-ttu-id="bf973-341">它是最佳内**ILyncClient.SignIn**和**ILyncClient.SignOut**方法，此属性设置，如下面的示例演示。</span><span class="sxs-lookup"><span data-stu-id="bf973-341">It is best to set this property within the **ILyncClient.SignIn** and **ILyncClient.SignOut** methods, as the following example demonstrates.</span></span> 
  
```cs
// This field is of a type that implements the 
// IAsynchronousOperation interface.
private IMClientAsyncOperation _asyncOperation = new IMClientAsyncOperation();
// This field is of a type that implements the ISelf interface.
private IMClientSelf _self;
public IMClientAsyncOperation SignIn(string _userUri, string _domainAndUser, 
    string _password, object _IMClientCallback, object _state)
{
    ClientState _previousClientState = this._clientState;
    this._clientState = ClientState.ucClientStateSignedIn;
    // The IMClientStateChangedEventData class implements the 
    // IClientStateChangedEventData interface.
    IMClientStateChangedEventData eventData = 
        new IMClientStateChangedEventData(_previousClientState, 
        this._clientState);
    if (_userUri != null)
    {
        // During the sign-in process, create a new contact with
        // the contact information of the currently signed-in user.
        this._self = new IMClientSelf(IMContact.BuildContact(_userUri));
    }
    // Raise the _ILyncClientEvents.OnStateChanged event.
    OnStateChanged(this, eventData as UC.ClientStateChangedEventData);
    
    return this._asyncOperation;
    }
}

```

<span data-ttu-id="bf973-342">下面的代码示例演示如何设置使用 _ **ILyncClientEvents**和 _ **IUCOfficeIntegrationEvents**接口的事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="bf973-342">The following code example demonstrates how to set up the event listener using the _ **ILyncClientEvents** and _ **IUCOfficeIntegrationEvents** interfaces.</span></span> 
  
```cs
using Microsoft.Office.Uc;
using System;
using System.Runtime.CompilerServices;
using System.Runtime.InteropServices;
namespace SampleImplementation
{
    // Note: UCOfficeIntegration inherits from both IUCOfficeIntegration and _IUCOfficeIntegrationEvents_Event
    [ClassInterface(ClassInterfaceType.None), Guid("13c41ef9-eb90-4e94-8a7c-1e9d686bc019"), ComVisible(true)]
    [ComSourceInterfaces(typeof(_IUCOfficeIntegrationEvents))]
    public class MyInstantMessengerOfficeIntegration : UCOfficeIntegration
    {
        #region IUCOfficeIntegration implementation
        public string GetAuthenticationInfo(string _version)
        {
            return "";
        }
        public object GetInterface(string _version, OIInterface _interface)
        {
            return null;
        }
        public OIFeature GetSupportedFeatures(string _version)
        {
            return OIFeature.oiFeatureAddOneNoteToConversation;
        }
        #endregion
        #region _IUCOfficeIntegrationEvents support
        // This event implements void _IUCOfficeIntegrationEvents.OnShuttingDown();
        public event _IUCOfficeIntegrationEvents_OnShuttingDownEventHandler OnShuttingDown;
        // This method is called by the IM application when it is beginning to shut down.
        // The method will raise the OnShuttingDown event which is translated by .NET COM interop layer
        // into a call to _IUCOfficeIntegrationEvents.OnShuttingDown.
        // This notifies Office applications that the IM application is going away.
        internal void RaiseOnShuttingDownEvent()
        {
            if (this.OnShuttingDown != null)
            {
                this.OnShuttingDown();
            }
        }
        #endregion
    }
    // Note: LyncClient inherits from both ILyncClient and _ILyncClientEvents_Event
    // You must implement LyncClient because the event handlers in _ILyncClientEvents expect you to pass a LyncClient interface.
    [ComVisible(true)]
    [ComSourceInterfaces(typeof(_ILyncClientEvents))]
    public class MyInstantMessengerOfficeIntegration2 :
        Client,
        Client2,
        LyncClient
    {
        #region Interfaces
        public LyncClientCapabilityTypes Capabilities
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ConferenceScheduler ConferenceScheduler
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ContactManager ContactManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ConversationManager ConversationManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public DelegatorClient[] DelegatorClients
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public DeviceManager DeviceManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public bool InSuppressedMode
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ContactManager PrivateContactManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public RoomManager RoomManager
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public Self Self
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ClientSettings Settings
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public SignInConfiguration SignInConfiguration
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ClientState State
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ClientType Type
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public string Uri
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public Utilities Utilities
        {
            get
            {
                throw new NotImplementedException();
            }
        }
        public ApplicationRegistration CreateApplicationRegistration(string _appGuid, string _appName)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation Initialize(string _clientName, string _version = "0", string _clientShortName = "0", string _clientNameAbbreviation = "0", string _clientLongName = "0", SupportedFeatures _supportedFeatures = SupportedFeatures.ucAllFeatures, [IUnknownConstant] object _CommunicatorClientCallback = null, object _state = null)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation Shutdown([IUnknownConstant] object _CommunicatorClientCallback, object _state)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation SignIn(string _userUri = "0", string _domainAndUsername = "0", string _password = "0", [IUnknownConstant] object _CommunicatorClientCallback = null, object _state = null)
        {
            throw new NotImplementedException();
        }
        public AsynchronousOperation SignOut([IUnknownConstant] object _CommunicatorClientCallback, object _state)
        {
            throw new NotImplementedException();
        }
        #endregion
        #region _ILyncClientEvents support
        public event _ILyncClientEvents_OnStateChangedEventHandler OnStateChanged;
        public event _ILyncClientEvents_OnNotificationReceivedEventHandler OnNotificationReceived;
        public event _ILyncClientEvents_OnCredentialRequestedEventHandler OnCredentialRequested;
        public event _ILyncClientEvents_OnSignInDelayedEventHandler OnSignInDelayed;
        public event _ILyncClientEvents_OnCapabilitiesChangedEventHandler OnCapabilitiesChanged;
        public event _ILyncClientEvents_OnDelegatorClientAddedEventHandler OnDelegatorClientAdded;
        public event _ILyncClientEvents_OnDelegatorClientRemovedEventHandler OnDelegatorClientRemoved;
        // Notifies Office apps that the IM client state (signed out, signing in, singed in, signing out, etc) has changed.
        internal void RaiseOnStateChangedEvent(ClientStateChangedEventData eventData)
        {
            if (this.OnStateChanged != null)
            {
                this.OnStateChanged(this, eventData);
            }
        }
        // Notifies Office apps that the IM client has received a notification event from MAPI (e.g. autodiscover has finished)
        internal void RaiseOnNotificationReceivedEvent(LyncClientNotificationReceivedEventData eventData)
        {
            if (this.OnNotificationReceived != null)
            {
                this.OnNotificationReceived(this, eventData);
            }
        }
        // Notifies Office apps that the IM client has received a request for credentials for some operation (e.g. sign in, web search)
        internal void RaiseOnCredentialRequestedEvent(CredentialRequestedEventData eventData)
        {
            if (this.OnCredentialRequested != null)
            {
                this.OnCredentialRequested(this, eventData);
            }
        }
        // Notifies Office apps that the IM client has been delayed from signing in and gives an estimated delay time.
        internal void RaiseOnSignInDelayedEvent(SignInDelayedEventData eventData)
        {
            if (this.OnSignInDelayed != null)
            {
                this.OnSignInDelayed(this, eventData);
            }
        }
        // Notifies Office apps that the capabilities of this IM client have changed.
        internal void RaiseOnCapabilitiesChangedEvent(PreferredCapabilitiesChangedEventData eventData)
        {
            if (this.OnCapabilitiesChanged != null)
            {
                this.OnCapabilitiesChanged(this, eventData);
            }
        }
        // Notifies Office apps that a DelegatorClient object has been added to the IM client object.
        internal void RaiseOnDelegatorClientAdded(DelegatorClientCollectionEventData eventData)
        {
            if (this.OnDelegatorClientAdded != null)
            {
                this.OnDelegatorClientAdded(this, eventData);
            }
        }
        // Notifies Office apps that a DelegatorClient object has been removed from the IM client object.
        internal void RaiseOnDelegatorClientRemoved(DelegatorClientCollectionEventData eventData)
        {
            if (this.OnDelegatorClientRemoved != null)
            {
                this.OnDelegatorClientRemoved(this, eventData);
            }
        }
        #endregion
    }
}
```

### <a name="iautomation-interface"></a><span data-ttu-id="bf973-343">IAutomation 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-343">IAutomation interface</span></span>
<span data-ttu-id="bf973-344"><a name="off15_IMIntegration_ImplementRequired_IAutomation"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-344"></span></span>

<span data-ttu-id="bf973-345">**IAutomation**界面自动化了 IM 客户端应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-345">The **IAutomation** interface automates features of the IM client application.</span></span> <span data-ttu-id="bf973-346">它可以用于开始对话，加入会议，并提供扩展性窗口上下文。</span><span class="sxs-lookup"><span data-stu-id="bf973-346">It can be used to start conversations, join conferences, and provide extensibility window context.</span></span> 
  
<span data-ttu-id="bf973-347">表 4 显示必须的继承**IAutomation**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-347">Table 4 shows the members that must be implemented in the class that inherits from **IAutomation**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-348">表中未列出的**IAutomation**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-348">Any member of the **IAutomation** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-349">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-349">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
> 
> <span data-ttu-id="bf973-350">有关**IAutomation**接口和其成员的详细信息，请参阅[UCCollaborationLib.IAutomation](http://msdn.microsoft.com/library/UCCollaborationLib.IAutomation)。</span><span class="sxs-lookup"><span data-stu-id="bf973-350">For more information about the **IAutomation** interface and its members, see [UCCollaborationLib.IAutomation](http://msdn.microsoft.com/library/UCCollaborationLib.IAutomation).</span></span> 
  
<span data-ttu-id="bf973-351">**表 4。IAutomation 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-351">**Table 4. Implementation of IAutomation interface**</span></span>

|<span data-ttu-id="bf973-352">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-352">**Member**</span></span>|<span data-ttu-id="bf973-353">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-353">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf973-354">**StartConversation**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-354">**StartConversation** method</span></span>  <br/> |<span data-ttu-id="bf973-355">开始使用指定的会话形式的对话。</span><span class="sxs-lookup"><span data-stu-id="bf973-355">Starts a conversation using the specified conversation modality.</span></span> <span data-ttu-id="bf973-356">返回**IConversationWindow**的实例。</span><span class="sxs-lookup"><span data-stu-id="bf973-356">An instance of **IConversationWindow** is returned.</span></span>  <br/> |
   
## <a name="implementing-contact-presence-integration"></a><span data-ttu-id="bf973-357">实现联系人的状态集成</span><span class="sxs-lookup"><span data-stu-id="bf973-357">Implementing contact presence integration</span></span>
<span data-ttu-id="bf973-358"><a name="off15_IMIntegration_ImplementIMFeatures"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-358"></span></span>

<span data-ttu-id="bf973-359">除了前面所述的三个所需接口，可以使用几个重要启用 Office 中的联系人的状态功能的其他接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-359">In addition to the three required interfaces discussed previously, there are several other interfaces that are important for enabling contact presence functionality in Office.</span></span> <span data-ttu-id="bf973-360">其中包括：</span><span class="sxs-lookup"><span data-stu-id="bf973-360">These include the following:</span></span>
  
- <span data-ttu-id="bf973-361">[IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact)或**IContact2**接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-361">The [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) or **IContact2** interface.</span></span> 
    
- <span data-ttu-id="bf973-362">[ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf)界面中。</span><span class="sxs-lookup"><span data-stu-id="bf973-362">The [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) interface.</span></span> 
    
- <span data-ttu-id="bf973-363">[IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager)和[_IContactManagerEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager)接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-363">The [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) and [_IContactManagerEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) interfaces.</span></span> 
    
- <span data-ttu-id="bf973-364">[IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)和[IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup)接口。</span><span class="sxs-lookup"><span data-stu-id="bf973-364">The [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) and [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) interfaces.</span></span> 
    
- <span data-ttu-id="bf973-365">[IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription)界面中。</span><span class="sxs-lookup"><span data-stu-id="bf973-365">The [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) interface.</span></span> 
    
- <span data-ttu-id="bf973-366">[IContactEndPoint](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactEndPoint)界面中。</span><span class="sxs-lookup"><span data-stu-id="bf973-366">The [IContactEndPoint](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactEndPoint) interface.</span></span> 
    
- <span data-ttu-id="bf973-367">[ILocaleString](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILocaleString)接口</span><span class="sxs-lookup"><span data-stu-id="bf973-367">The [ILocaleString](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILocaleString) interface</span></span> 
    
### <a name="icontact-interface"></a><span data-ttu-id="bf973-368">IContact 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-368">IContact interface</span></span>
<span data-ttu-id="bf973-369"><a name="off15_IMIntegration_ImplementRequired_IContact"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-369"></span></span>

<span data-ttu-id="bf973-370">**IContact**界面代表 IM 客户端应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="bf973-370">The **IContact** interface represents an IM client application user.</span></span> <span data-ttu-id="bf973-371">接口公开状态、 可用的形式、 组成员身份和用户的联系人类型属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-371">The interface exposes presence, available modalities, group membership, and contact type properties for a user.</span></span> <span data-ttu-id="bf973-372">与另一个用户开始对话，您必须提供**IContact**该用户实例。</span><span class="sxs-lookup"><span data-stu-id="bf973-372">To start a conversation with another user, you must provide that user instance of **IContact**.</span></span>
  
<span data-ttu-id="bf973-373">表 5 显示了必须的继承**IContact**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-373">Table 5 shows the members that must be implemented in the class that inherits from **IContact**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-374">表中未列出的**IContact**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-374">Any member of the **IContact** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-375">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-375">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
>
> <span data-ttu-id="bf973-376">有关**IContact**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContact](http://msdn.microsoft.com/library/UCCollaborationLib.IContact)。</span><span class="sxs-lookup"><span data-stu-id="bf973-376">For more information about the **IContact** interface and its members, see [UCCollaborationLib.IContact](http://msdn.microsoft.com/library/UCCollaborationLib.IContact).</span></span> 
  
<span data-ttu-id="bf973-377">**表 5。IContact 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-377">**Table 5. Implementation of the IContact interface**</span></span>

|<span data-ttu-id="bf973-378">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-378">**Member**</span></span>|<span data-ttu-id="bf973-379">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-379">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf973-380">**CanStart**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-380">**CanStart** method</span></span>  <br/> |<span data-ttu-id="bf973-381">如果可以在该联系人上启动给定的类型的形式，则返回**true** 。</span><span class="sxs-lookup"><span data-stu-id="bf973-381">Returns **true** if a given type of modality can be started on the contact.</span></span>  <br/> |
|<span data-ttu-id="bf973-382">**GetContactInformation**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-382">**GetContactInformation** method</span></span>  <br/> |<span data-ttu-id="bf973-383">从发布联系人获取一个状态项。</span><span class="sxs-lookup"><span data-stu-id="bf973-383">Gets one presence item from a publishing contact.</span></span>  <br/> |
|<span data-ttu-id="bf973-384">**BatchGetContactInformation**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-384">**BatchGetContactInformation** method</span></span>  <br/> |<span data-ttu-id="bf973-385">从发布联系人获取多个状态项目。</span><span class="sxs-lookup"><span data-stu-id="bf973-385">Gets multiple presence items from a publishing contact.</span></span>  <br/> |
|<span data-ttu-id="bf973-386">**Settings**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-386">**Settings** property</span></span>  <br/> |<span data-ttu-id="bf973-387">获取联系人属性的集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-387">Gets a collection of contact properties.</span></span>  <br/> |
|<span data-ttu-id="bf973-388">**CustomGroups**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-388">**CustomGroups** property</span></span>  <br/> |<span data-ttu-id="bf973-389">获取组的成员的联系人的集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-389">Gets a collection of groups that the contact is a member of.</span></span>  <br/> |
   
<span data-ttu-id="bf973-390">在初始化过程中，Office 应用程序调用**IContact.CanStart**方法来确定本地用户的 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="bf973-390">During the initialization process, the Office application calls the **IContact.CanStart** method to determine the IM capabilities for the local user.</span></span> <span data-ttu-id="bf973-391">**CanStart**方法所需的 __modalityTypes_形参的实参作为[UCCollaborationLib.ModalityTypes](http://msdn.microsoft.com/library/UCCollaborationLib.ModalityTypes)枚举中的标志。</span><span class="sxs-lookup"><span data-stu-id="bf973-391">The **CanStart** method takes a flag from the [UCCollaborationLib.ModalityTypes](http://msdn.microsoft.com/library/UCCollaborationLib.ModalityTypes) enumeration as an argument for the  __modalityTypes_ parameter.</span></span> <span data-ttu-id="bf973-392">如果当前用户可以参与请求形式 （即，用户是支持即时消息、 音频和视频消息，或应用程序共享的）， **CanStart**方法返回**true**。</span><span class="sxs-lookup"><span data-stu-id="bf973-392">If the current user can engage in the requested modality (that is, the user is capable of instant messaging, audio and video messaging, or application sharing), the **CanStart** method returns **true**.</span></span>
  
```cs
public bool CanStart(ModalityTypes _modalityTypes)
{
    // Define the capabilities of the current IM client application
    // user by using flags from the ModalityTypes enumeration.
    ModalityTypes userCapabilities = 
        ModalityTypes.ucModalityInstantMessage | 
        ModalityTypes.ucModalityAudioVideo | 
        ModalityTypes.ucModalityAppSharing;
    // Perform a simple test for equivalency.
    if (_modalityType == userCapabilities) 
    {
        return true;
    }
    else 
    {
        return false;
    }
}

```

<span data-ttu-id="bf973-393">**GetContactInformation**方法从**IContact**对象检索有关该联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="bf973-393">The **GetContactInformation** method retrieves information about the contact from the **IContact** object.</span></span> <span data-ttu-id="bf973-394">调用的代码需要在值传递 __contactInformationType_参数，指示要检索的数据的[UCCollaborationLib.ContactInformationType](http://msdn.microsoft.com/library/UCCollaborationLib.ContactInformationType)枚举中。</span><span class="sxs-lookup"><span data-stu-id="bf973-394">The calling code needs to pass in a value from the [UCCollaborationLib.ContactInformationType](http://msdn.microsoft.com/library/UCCollaborationLib.ContactInformationType) enumeration for the  __contactInformationType_ parameter, which indicates the data to be retrieved.</span></span> 
  
```cs
public object GetContactInformation(
    ContactInformationType _contactInformationType)
{
    // Determine the information to return from the contact's data based
    // on the value passed in for the _contactInformationType parameter.
    switch (_contactInformationType)
    {
        case ContactInformationType.ucPresenceEmailAddresses:
        {
            // Return the URI associated with the contact.
            string returnValue = this.Uri.ToLower().Replace("sip:", String.Empty);
            return returnValue;
        }
        case ContactInformationType.ucPresenceDisplayName:
        {
            // Return the display name associated with the contact.
            string returnValue = this._DisplayName;
            return returnValue;
        }
        default:
        {
            throw new NotImplementedException;
        }
        // Additional implementation details omitted.
    }
}
```

<span data-ttu-id="bf973-395">类似于**GetContactInformation**， **BatchGetContactInformation**方法检索有关该联系人的多个状态项目从**IContact**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-395">Similar to the **GetContactInformation**, the **BatchGetContactInformation** method retrieves multiple presence items about the contact from the **IContact** object.</span></span> <span data-ttu-id="bf973-396">调用的代码需要从**ContactInformationType**枚举 __contactInformationTypes_参数传递的值的数组中。</span><span class="sxs-lookup"><span data-stu-id="bf973-396">The calling code needs to pass in an array of values from the **ContactInformationType** enumeration for the  __contactInformationTypes_ parameter.</span></span> <span data-ttu-id="bf973-397">该方法返回[UCCollaborationLib.IContactInformationDictionary](http://msdn.microsoft.com/library/UCCollaborationLib.IContactInformationDictionary)对象，其中包含请求的数据。</span><span class="sxs-lookup"><span data-stu-id="bf973-397">The method returns an [UCCollaborationLib.IContactInformationDictionary](http://msdn.microsoft.com/library/UCCollaborationLib.IContactInformationDictionary) object that contains the requested data.</span></span> 
  
```cs
public IMClientContactInformationDictionary BatchGetContactInformation(
    ContactInformationType[] _contactInformationTypes)
{
    // The IMClientContactInformationDictionary class implements the
    // IContactInformationDictionary interface.
    IMClientContactInformationDictionary contactDictionary = 
        new IMClientContactInformationDictionary();
    foreach (ContactInformationType type in _contactInformationTypes)
    {
        // Call GetContactInformation for each type of contact 
        // information to retrieve. This code adds a new entry to
        // a Dictionary object exposed by the
        // ContactInformationDictionary property.
        contactDictionary.ContactInformationDictionary.Add(
            type, this.GetContactInformation(type));
    }
    return contactDictionary;
}
```

<span data-ttu-id="bf973-398">**IContact.Settings**属性返回**IContactSettingDictionary**对象，该对象包含有关该联系人的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-398">The **IContact.Settings** property returns an **IContactSettingDictionary** object that contains custom properties about the contact.</span></span> 
  
```cs
public IMClientContactSettingDictionary Settings
{
    get
    {
       // The IMClientContactSettingDictionary class implements
       // the IContactSettingDictionary interface.
       return new IMClientContactSettingDictionary();
    }
}
```

<span data-ttu-id="bf973-399">**IContact.CustomGroups**属性返回**IGroupCollection**对象，该对象包含所有联系人是其成员的组。</span><span class="sxs-lookup"><span data-stu-id="bf973-399">The **IContact.CustomGroups** property returns an **IGroupCollection** object that includes all of the groups of which the contact is a member.</span></span> 
  
```cs
public IMClientGroupCollection CustomGroups
{
    get {
       // The IMClientGroupCollection class implements
       // the IGroupCollection interface.
        return new IMClientGroupCollection();
    }
}
```

### <a name="iself-interface"></a><span data-ttu-id="bf973-400">ISelf 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-400">ISelf interface</span></span>
<span data-ttu-id="bf973-401"><a name="off15_IMIntegration_ImplementRequired_ISelf"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-401"></span></span>

<span data-ttu-id="bf973-402">在初始化过程中，Office 应用程序获取的数据为当前用户通过访问必须返回**ISelf**对象的**ILyncClient.Self**属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-402">During the initialization process, the Office application gets the data for the current user by accessing the **ILyncClient.Self** property, which must return an **ISelf** object.</span></span> <span data-ttu-id="bf973-403">**ISelf**界面代表本地、 已登录的 IM 客户端应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="bf973-403">The **ISelf** interface represents the local, signed-in IM client application user.</span></span> 
  
<span data-ttu-id="bf973-404">表 6 显示必须的继承**ISelf**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-404">Table 6 shows the members that must be implemented in the class that inherits from **ISelf**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-405">表中未列出的**ISelf**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-405">Any member of the **ISelf** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-406">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-406">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
  
<span data-ttu-id="bf973-407">**表 6。ISelf 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-407">**Table 6. Implementation of the ISelf interface**</span></span>

|<span data-ttu-id="bf973-408">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-408">**Member**</span></span>|<span data-ttu-id="bf973-409">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-409">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf973-410">**联系人**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-410">**Contact** property</span></span>  <br/> |<span data-ttu-id="bf973-411">获取与本地用户关联的**IContact**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-411">Gets the **IContact** object associated with the local user.</span></span>  <br/> |
   
<span data-ttu-id="bf973-412">通过的**ISelf.Contact**属性 （返回**IContact**对象） 公开状态、 可用的形式、 组成员和本地用户的联系人类型属性。</span><span class="sxs-lookup"><span data-stu-id="bf973-412">Presence, available modalities, group membership, and contact type properties for the local user are exposed through the **ISelf.Contact** property (which returns an **IContact** object).</span></span> <span data-ttu-id="bf973-413">在初始化过程中，Office 应用程序访问**ISelf.Contact**属性来获取对本地用户的联系人信息的引用。</span><span class="sxs-lookup"><span data-stu-id="bf973-413">During the initialization process, the Office application accesses the **ISelf.Contact** property to get a reference to the contact information for the local user.</span></span> 
  
<span data-ttu-id="bf973-414">使用以下代码定义从**ISelf**接口实现**联系人**属性继承的类。</span><span class="sxs-lookup"><span data-stu-id="bf973-414">Use the following code to define a class that inherits from the **ISelf** interface that implements the **Contact** property.</span></span> 
  
```cs
[ComVisible(true)]
public class IMClientSelf : ISelf
{
    // Declare a private field to store contact data for local user.
    private IMClientContact _contactData;
    // In the constructor for the ISelf object, the calling code 
    // must supply contact data.
    public IMClientSelf (IMClientContact _selfContactData)
    {
        this._contactData = _selfContactData;
    }
    // When accessed, the Contact property returns a reference
    // to the IContact object that represents the local user.
    public IMClientContact Contact
    {
        get
        {
            return this._contactData as IMClientContact;
        }
    }
    // Additional implementation details omitted.
}
```

### <a name="icontactmanager-and-icontactmanagerevents-interfaces"></a><span data-ttu-id="bf973-415">IContactManager 和 _IContactManagerEvents 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-415">IContactManager and _IContactManagerEvents interfaces</span></span>
<span data-ttu-id="bf973-416"><a name="off15_IMIntegration_ImplementRequired_IContactManager"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-416"></span></span>

<span data-ttu-id="bf973-417">**IContactManager**对象管理本地用户，包括本地用户自己的联系人信息的联系人。</span><span class="sxs-lookup"><span data-stu-id="bf973-417">The **IContactManager** object manages the contacts for the local user, including the local user's own contact information.</span></span> <span data-ttu-id="bf973-418">Office 应用程序使用**IContactManager**对象访问**IContact**对象对应于本地用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="bf973-418">The Office application uses an **IContactManager** object to access **IContact** objects that correspond to the local user's contacts.</span></span> 
  
<span data-ttu-id="bf973-419">表 7 显示了必须继承自**IContactManager**和 **_IContactManagerEvents**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-419">Table 7 shows the members that must be implemented in the class that inherits from **IContactManager** and **_IContactManagerEvents**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-420">表中未列出的**IContactManager**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-420">Any member of the **IContactManager** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-421">已存在，但未实现的成员可以引发**NotImplementedException**或**E\_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-421">Members that are present but not implemented can throw a **NotImplementedException** or **E\_NOTIMPL** error.</span></span> 
>
> <span data-ttu-id="bf973-422">有关**IContactManager** **_IContactManagerEvents**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContactManager](http://msdn.microsoft.com/library/UCCollaborationLib.IContactManager)和[UCCollaborationLib._IContactManagerEvents](http://msdn.microsoft.com/library/UCCollaborationLib._IContactManagerEvents)。</span><span class="sxs-lookup"><span data-stu-id="bf973-422">For more information about the **IContactManager** and **_IContactManagerEvents** interfaces and their members, see [UCCollaborationLib.IContactManager](http://msdn.microsoft.com/library/UCCollaborationLib.IContactManager) and [UCCollaborationLib._IContactManagerEvents](http://msdn.microsoft.com/library/UCCollaborationLib._IContactManagerEvents).</span></span> 
  
<span data-ttu-id="bf973-423">**表 7。IContactManager 和 _IContactManagerEvents 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-423">**Table 7. Implementation of the IContactManager and _IContactManagerEvents interfaces**</span></span>

|<span data-ttu-id="bf973-424">**接口**</span><span class="sxs-lookup"><span data-stu-id="bf973-424">**Interface**</span></span>|<span data-ttu-id="bf973-425">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-425">**Member**</span></span>|<span data-ttu-id="bf973-426">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-426">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf973-427">**IContactManager**</span><span class="sxs-lookup"><span data-stu-id="bf973-427">**IContactManager**</span></span> <br/> |<span data-ttu-id="bf973-428">**GetContactByUri**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-428">**GetContactByUri** method</span></span>  <br/> |<span data-ttu-id="bf973-429">查找或使用联系人 URI 创建新的联系人实例。</span><span class="sxs-lookup"><span data-stu-id="bf973-429">Finds or creates a new contact instance by using the contact URI.</span></span>  <br/> |
||<span data-ttu-id="bf973-430">**CreateSubscription**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-430">**CreateSubscription** method</span></span>  <br/> |<span data-ttu-id="bf973-431">创建一个可用于批处理订阅或查询的**ISubscription**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-431">Creates an **ISubscription** object that can be used for batching subscriptions or queries.</span></span>  <br/> |
||<span data-ttu-id="bf973-432">**Lookup**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-432">**Lookup** method</span></span>  <br/> |<span data-ttu-id="bf973-433">查找联系人或通讯组。</span><span class="sxs-lookup"><span data-stu-id="bf973-433">Looks up a contact or distribution group.</span></span>  <br/> |
|<span data-ttu-id="bf973-434">**_IContactManagerEvents**</span><span class="sxs-lookup"><span data-stu-id="bf973-434">**_IContactManagerEvents**</span></span> <br/> |<span data-ttu-id="bf973-435">**OnGroupAdded**事件</span><span class="sxs-lookup"><span data-stu-id="bf973-435">**OnGroupAdded** event</span></span>  <br/> |<span data-ttu-id="bf973-436">一组添加到组集合时引发。</span><span class="sxs-lookup"><span data-stu-id="bf973-436">Raised when a group is added to a group collection.</span></span> <span data-ttu-id="bf973-437">可以从**IContactManager.Groups**属性获取更新的组集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-437">The updated group collection can be obtained from the **IContactManager.Groups** property.</span></span>  <br/> |
||<span data-ttu-id="bf973-438">**OnGroupRemoved**事件</span><span class="sxs-lookup"><span data-stu-id="bf973-438">**OnGroupRemoved** event</span></span>  <br/> |<span data-ttu-id="bf973-439">从一组中删除组时引发。</span><span class="sxs-lookup"><span data-stu-id="bf973-439">Raised when a group is removed from a group collection.</span></span> <span data-ttu-id="bf973-440">可以从**IContactManager.Groups**属性获取更新的组集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-440">The updated group collection can be obtained from the **IContactManager.Groups** property.</span></span>  <br/> |
||<span data-ttu-id="bf973-441">**OnSearchProviderStateChanged**事件</span><span class="sxs-lookup"><span data-stu-id="bf973-441">**OnSearchProviderStateChanged** event</span></span>  <br/> |<span data-ttu-id="bf973-442">搜索提供程序的状态发生变化时引发。</span><span class="sxs-lookup"><span data-stu-id="bf973-442">Raised when a search provider's status changes.</span></span>  <br/> |
   
<span data-ttu-id="bf973-443">Office 调用**IContactManager.GetContactByUri**获取联系人的状态信息，使用该联系人的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="bf973-443">Office calls **IContactManager.GetContactByUri** to get a contact's presence information, by using the SIP address of the contact.</span></span> <span data-ttu-id="bf973-444">当联系人配置为在 Active Directory 中的 SIP 地址时，Office 将确定此地址的联系人和呼叫**GetContactByUri**，传递此 __contactUri_参数中的联系人的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="bf973-444">When a contact is configured for an SIP address in the Active Directory, Office determines this address for a contact and calls **GetContactByUri**, passing the SIP address of the contact in for the  __contactUri_ parameter.</span></span> 
  
<span data-ttu-id="bf973-445">当 Office 无法确定联系人的 SIP 地址时，它会调用**IContactManager.Lookup**方法使用 IM 服务查找 SIP。</span><span class="sxs-lookup"><span data-stu-id="bf973-445">When Office cannot determine the SIP address for the contact, it calls the **IContactManager.Lookup** method to find the SIP by using the IM service.</span></span> <span data-ttu-id="bf973-446">此处 Office 传入它能找到该联系人 （例如，只需为该联系人的电子邮件地址） 的最佳数据。</span><span class="sxs-lookup"><span data-stu-id="bf973-446">Here Office passes in the best data that it can find for the contact (for example, just the email address for the contact).</span></span> <span data-ttu-id="bf973-447">**Lookup**方法异步返回**AsynchronousOperation**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-447">The **Lookup** method asynchronously returns an **AsynchronousOperation** object.</span></span> <span data-ttu-id="bf973-448">当调用回调时，该**查阅**方法应返回联系人除了 URI 的操作成功与否。</span><span class="sxs-lookup"><span data-stu-id="bf973-448">When it invokes the callback, the **Lookup** method should return the success or failure of the operation in addition to the URI of the contact.</span></span> 
  
```cs
public IMClientContact GetContactByUri(string _contactUri)
{
    // Declare a Contact variable to contain information about the contact.
    IMClientContact tempContact = null;
    // The _groupCollections field is an IGroupCollection object. Iterate 
    // over each group in collection to see if the 
    // contact is a part of the group.
    foreach (IMClientGroup group in this._groupCollections)
    {
       if (group.TryGetContact(_contactUri, out tempContact))
       {
           break;
       }
    }
    // Check to see that the URI returned a valid contact. If it
    // did not, create a new contact.
    if (tempContact == null)
    {
        tempContact = IMClientContact.BuildContact(_contactUri);
    }
    // Return the contact to the calling code.
    return tempContact;
}
```

<span data-ttu-id="bf973-449">Office 应用程序需要订阅的单个联系人的状态更改。</span><span class="sxs-lookup"><span data-stu-id="bf973-449">The Office application needs to subscribe to presence changes for an individual contact.</span></span> <span data-ttu-id="bf973-450">因此，联系人的状态更改时，IM 服务器通知 IM 客户端应用程序，从而警报的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf973-450">Thus, when a contact's presence status changes, the IM server alerts the IM client application—thereby alerting the Office application.</span></span> <span data-ttu-id="bf973-451">若要执行此操作，Office 应用程序，请调用**IContactManager.CreateSubscription**方法可创建的此请求的新**IContactSubscription**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-451">To do this, the Office application calls the **IContactManager.CreateSubscription** method to create a new **IContactSubscription** object for this request.</span></span> 
  
```cs
// Declare a private field to contain an IContactSubscription object.
private IMClientContactSubscription _contactSubscription;
// Return the IContactSubscription object associated 
// with the IContactManager object.
public IMClientContactSubscription CreateSubscription()
{
    return this._contactSubscription;
}
```

### <a name="igroup-and-igroupcollection-interfaces"></a><span data-ttu-id="bf973-452">IGroup 和 IGroupCollection 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-452">IGroup and IGroupCollection interfaces</span></span>
<span data-ttu-id="bf973-453"><a name="off15_IMIntegration_ImplementRequired_IGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-453"></span></span>

<span data-ttu-id="bf973-454">**IGroup**对象代表与其他属性确定联系人集合通过集体组名的联系人的集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-454">The **IGroup** object represents a collection of contacts with additional properties for identifying the contact collection by a collective group name.</span></span> <span data-ttu-id="bf973-455">**IGroupCollection**对象代表由本地用户和 IM 客户端应用程序定义的**IGroup**对象的集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-455">An **IGroupCollection** object represents a collection of **IGroup** objects defined by a local user and the IM client application.</span></span> <span data-ttu-id="bf973-456">Office 应用程序使用的**IGroupCollection**和**IGroup**对象来访问本地用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="bf973-456">The Office application uses the **IGroupCollection** and **IGroup** objects to access the local user's contacts.</span></span> 
  
<span data-ttu-id="bf973-457">表 9 显示了必须在下表中从**IGroup**和**IGroupCollection**继承的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-457">Table 9 shows the members that must be implemented in the classes that inherit from **IGroup** and **IGroupCollection** in the following table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf973-458">表中未列出的**IGroup**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-458">Any member of the **IGroup** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-459">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-459">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
>
> <span data-ttu-id="bf973-460">有关的**IGroup**和**IGroupCollection**接口及其成员的详细信息，请参阅[UCCollaborationLib.IGroup](http://msdn.microsoft.com/library/UCCollaborationLib.IGroup)和[UCCollaborationLib.IGroupCollection](http://msdn.microsoft.com/library/UCCollaborationLib.IGroupCollection)。</span><span class="sxs-lookup"><span data-stu-id="bf973-460">For more information about the **IGroup** and **IGroupCollection** interfaces and their members, see [UCCollaborationLib.IGroup](http://msdn.microsoft.com/library/UCCollaborationLib.IGroup) and [UCCollaborationLib.IGroupCollection](http://msdn.microsoft.com/library/UCCollaborationLib.IGroupCollection).</span></span> 
  
<span data-ttu-id="bf973-461">**表 9。IGroup 和 IGroupCollection 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-461">**Table 9. Implementation of the IGroup and IGroupCollection interfaces**</span></span>

|<span data-ttu-id="bf973-462">**接口**</span><span class="sxs-lookup"><span data-stu-id="bf973-462">**Interface**</span></span>|<span data-ttu-id="bf973-463">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-463">**Member**</span></span>|<span data-ttu-id="bf973-464">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-464">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf973-465">**IGroupCollection**</span><span class="sxs-lookup"><span data-stu-id="bf973-465">**IGroupCollection**</span></span> <br/> |<span data-ttu-id="bf973-466">**Count** 属性</span><span class="sxs-lookup"><span data-stu-id="bf973-466">**Count** property</span></span>  <br/> |<span data-ttu-id="bf973-467">返回集合中的**IGroup**对象的计数</span><span class="sxs-lookup"><span data-stu-id="bf973-467">Returns the count of **IGroup** objects in the collection</span></span>  <br/> |
||<span data-ttu-id="bf973-468">**Item** 属性</span><span class="sxs-lookup"><span data-stu-id="bf973-468">**Item** property</span></span>  <br/> |<span data-ttu-id="bf973-469">返回集合中指定索引处的**IGroup**对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-469">Returns the **IGroup** object at the specified index in the collection.</span></span>  <br/> |
|<span data-ttu-id="bf973-470">**IGroup**</span><span class="sxs-lookup"><span data-stu-id="bf973-470">**IGroup**</span></span> <br/> |<span data-ttu-id="bf973-471">**Id**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-471">**Id** property</span></span>  <br/> |<span data-ttu-id="bf973-472">返回组中的 ID。</span><span class="sxs-lookup"><span data-stu-id="bf973-472">Returns the ID of the group.</span></span>  <br/> |
   
<span data-ttu-id="bf973-473">时 Office 应用程序获取本地用户的信息，它通过调用返回**IGroupCollection**对象的**IContact.CustomGroups**属性来访问联系人 （本地用户） 的组成员资格。</span><span class="sxs-lookup"><span data-stu-id="bf973-473">When the Office application gets the information for the local user, it accesses the group memberships of the contact (local user) by calling the **IContact.CustomGroups** property, which returns an **IGroupCollection** object.</span></span> <span data-ttu-id="bf973-474">**IGroupCollection**必须包含**IGroup**对象的数组 （或**列表**）。</span><span class="sxs-lookup"><span data-stu-id="bf973-474">The **IGroupCollection** must contain an array (or **List**) of **IGroup** objects.</span></span> <span data-ttu-id="bf973-475">从**IGroupCollection**派生的类必须公开**Count**属性，该集合和索引器方法， **this(int)**，从集合中返回一个**IGroup**对象中返回的项目数。</span><span class="sxs-lookup"><span data-stu-id="bf973-475">The class that derives from **IGroupCollection** must expose a **Count** property, which returns the number of items in the collection, and an indexer method, **this(int)**, which returns an **IGroup** object from the collection.</span></span> 
  
### <a name="icontactsubscription-interface"></a><span data-ttu-id="bf973-476">IContactSubscription 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-476">IContactSubscription interface</span></span>
<span data-ttu-id="bf973-477"><a name="off15_IMIntegration_ImplementRequired_IContactSubscription"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-477"></span></span>

<span data-ttu-id="bf973-478">**IContactSubscription**界面允许您指定要接收有关更新的状态信息和触发通知的类型的状态信息的联系人。</span><span class="sxs-lookup"><span data-stu-id="bf973-478">The **IContactSubscription** interface allows you to specify the contacts to receive presence information updates for and the types of presence information that trigger a notification.</span></span> <span data-ttu-id="bf973-479">Office 应用程序使用**IContactSubscription**对象注册更改联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-479">Office applications use an **IContactSubscription** object to register changes to contact's presence status.</span></span> 
  
<span data-ttu-id="bf973-480">表 10 显示必须继承**IContactSubscription**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-480">Table 10 shows the members that must be implemented in the classes that inherit from **IContactSubscription**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-481">表中未列出的**IContactSubscription**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-481">Any member of the **IContactSubscription** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-482">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-482">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span>
>
> <span data-ttu-id="bf973-483">有关**IContactSubscription**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContactSubscription](http://msdn.microsoft.com/library/UCCollaborationLib.IContactSubscription)。</span><span class="sxs-lookup"><span data-stu-id="bf973-483">For more information about the **IContactSubscription** interface and its members, see [UCCollaborationLib.IContactSubscription](http://msdn.microsoft.com/library/UCCollaborationLib.IContactSubscription).</span></span> 
  
<span data-ttu-id="bf973-484">**表 10。IContactSubscription 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-484">**Table 10. Implementation of the IContactSubscription interface**</span></span>

|<span data-ttu-id="bf973-485">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-485">**Member**</span></span>|<span data-ttu-id="bf973-486">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-486">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf973-487">**AddContact**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-487">**AddContact** method</span></span>  <br/> |<span data-ttu-id="bf973-488">将联系人添加到订阅对象。</span><span class="sxs-lookup"><span data-stu-id="bf973-488">Adds a contact to the subscription object.</span></span>  <br/> |
|<span data-ttu-id="bf973-489">**Subscribe**方法</span><span class="sxs-lookup"><span data-stu-id="bf973-489">**Subscribe** method</span></span>  <br/> |<span data-ttu-id="bf973-490">帮助 IM 客户端应用程序监视联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-490">Helps the IM client application to monitor presence for a contact.</span></span>  <br/> |
   
<span data-ttu-id="bf973-491">**IContactSubscription**接口必须包含对监视，使用数组或**列表**的所有**IContact**对象的引用。</span><span class="sxs-lookup"><span data-stu-id="bf973-491">The **IContactSubscription** interface must contain a reference to all the **IContact** objects that it monitors, using an array or a **List**.</span></span> <span data-ttu-id="bf973-492">**IContactSubscription.AddContact**方法添加**IContact**对象**IContactSubscription**对象的基础数据结构，从而添加新联系人的状态更改监视。</span><span class="sxs-lookup"><span data-stu-id="bf973-492">The **IContactSubscription.AddContact** method adds an **IContact** object for the to the underlying data structure of the **IContactSubscription** object, thereby adding a new contact to monitor for presence changes.</span></span> 
  
```cs
// Store references to all of the IContact objects to subscribe to.
private List<IMClientContact> _subscribedContacts;
// Add a new IContact object to the collection of contacts.
public void AddContact(IMClientContact _contact)
{
    this._subscribedContacts.Add(_contact);
}
```

<span data-ttu-id="bf973-493">**IContactSubscription.Subscribe**方法允许访问联系人的状态观察者 IM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf973-493">The **IContactSubscription.Subscribe** method allows an IM client application to access presence observers for the contact.</span></span> <span data-ttu-id="bf973-494">它可以使用的轮询策略获取订阅 IM 客户端应用程序中的服务器的联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-494">It can use a polling strategy to get the presence from the server for the contacts for that the IM client application has subscribed to.</span></span> <span data-ttu-id="bf973-495">在其中为外部用户的联系人列表 （例如，从较大的公用网络） 的某个人的请求状态的情况下有用的**Subscribe**方法。</span><span class="sxs-lookup"><span data-stu-id="bf973-495">The **Subscribe** method is helpful in situations where presence is requested for someone outside of a user's contact list (for example, from a larger public network).</span></span> 
  
### <a name="icontactendpoint-interface"></a><span data-ttu-id="bf973-496">IContactEndPoint 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-496">IContactEndPoint interface</span></span>
<span data-ttu-id="bf973-497"><a name="off15_IMIntegration_ImplementRequired_IContactEndPoint"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-497"></span></span>

<span data-ttu-id="bf973-498">**IContactEndPoint**表示电话号码的电话号码的联系人的集合中。</span><span class="sxs-lookup"><span data-stu-id="bf973-498">The **IContactEndPoint** represents a telephone number from a contact's collection of telephone numbers.</span></span> 
  
<span data-ttu-id="bf973-499">表 11 显示了必须在从**IContactEndPoint**继承的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-499">Table 11 shows the members that must be implemented in the classes that inherit from **IContactEndPoint**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-500">表中未列出的**IContactEndPoint**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-500">Any member of the **IContactEndPoint** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-501">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-501">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span>
>
> <span data-ttu-id="bf973-502">有关**IContactEndPoint**接口和其成员的详细信息，请参阅[UCCollaborationLib.IContactEndpoint](http://msdn.microsoft.com/library/UCCollaborationLib.IContactEndpoint)。</span><span class="sxs-lookup"><span data-stu-id="bf973-502">For more information about the **IContactEndPoint** interface and its members, see [UCCollaborationLib.IContactEndpoint](http://msdn.microsoft.com/library/UCCollaborationLib.IContactEndpoint).</span></span> 
  
<span data-ttu-id="bf973-503">**表 11。IContactEndPoint 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-503">**Table 11. Implementation of the IContactEndPoint interface**</span></span>

|<span data-ttu-id="bf973-504">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-504">**Member**</span></span>|<span data-ttu-id="bf973-505">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-505">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf973-506">**DisplayName**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-506">**DisplayName** property</span></span>  <br/> |<span data-ttu-id="bf973-507">获取显示字符串。</span><span class="sxs-lookup"><span data-stu-id="bf973-507">Gets the display string.</span></span>  <br/> |
|<span data-ttu-id="bf973-508">**Type** 属性</span><span class="sxs-lookup"><span data-stu-id="bf973-508">**Type** property</span></span>  <br/> |<span data-ttu-id="bf973-509">获取联系人的终结点类型</span><span class="sxs-lookup"><span data-stu-id="bf973-509">Gets the contact endpoint type</span></span>  <br/> |
|<span data-ttu-id="bf973-510">**Uri** 属性</span><span class="sxs-lookup"><span data-stu-id="bf973-510">**Uri** property</span></span>  <br/> |<span data-ttu-id="bf973-511">获取联系人的 URI。</span><span class="sxs-lookup"><span data-stu-id="bf973-511">Gets the contact URI.</span></span>  <br/> |
   
### <a name="ilocalestring-interface"></a><span data-ttu-id="bf973-512">ILocaleString 接口</span><span class="sxs-lookup"><span data-stu-id="bf973-512">ILocaleString interface</span></span>
<span data-ttu-id="bf973-513"><a name="off15_IMIntegration_ImplementRequired_ILocaleString"> </a></span><span class="sxs-lookup"><span data-stu-id="bf973-513"></span></span>

<span data-ttu-id="bf973-514">**ILocaleString**是包含的本地化的字符串和本地化的区域设置 ID 的本地化的字符串结构。</span><span class="sxs-lookup"><span data-stu-id="bf973-514">The **ILocaleString** is a localized string structure that contains both a localized string and the locale ID of the localization.</span></span> <span data-ttu-id="bf973-515">**ILocaleString**接口用于设置联系人卡片上的自定义状态字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="bf973-515">The **ILocaleString** interface is used to format the custom status string on the contact card.</span></span> 
  
<span data-ttu-id="bf973-516">表 12 显示必须继承**ILocaleString**类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="bf973-516">Table 12 shows the members that must be implemented in the classes that inherit from **ILocaleString**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf973-517">表中未列出的**ILocaleString**任何的接口成员必须存在但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="bf973-517">Any member of the **ILocaleString** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="bf973-518">已存在，但未实现的成员可以引发**NotImplementedException**或**E_NOTIMPL**错误。</span><span class="sxs-lookup"><span data-stu-id="bf973-518">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span>
>
> <span data-ttu-id="bf973-519">有关**ILocalString**接口和其成员的详细信息，请参阅[UCCollaborationLib.ILocaleString](http://msdn.microsoft.com/library/UCCollaborationLib.ILocaleString)。</span><span class="sxs-lookup"><span data-stu-id="bf973-519">For more information about the **ILocalString** interface and its members, see [UCCollaborationLib.ILocaleString](http://msdn.microsoft.com/library/UCCollaborationLib.ILocaleString).</span></span> 
  
<span data-ttu-id="bf973-520">**表 12。ILocaleString 接口实现**</span><span class="sxs-lookup"><span data-stu-id="bf973-520">**Table 12. Implementation of the ILocaleString interface**</span></span>

|<span data-ttu-id="bf973-521">**成员**</span><span class="sxs-lookup"><span data-stu-id="bf973-521">**Member**</span></span>|<span data-ttu-id="bf973-522">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf973-522">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf973-523">**LocaleId**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-523">**LocaleId** property</span></span>  <br/> |<span data-ttu-id="bf973-524">获取区域设置 id。</span><span class="sxs-lookup"><span data-stu-id="bf973-524">Gets the locale ID.</span></span>  <br/> |
|<span data-ttu-id="bf973-525">**Value**属性</span><span class="sxs-lookup"><span data-stu-id="bf973-525">**Value** property</span></span>  <br/> |<span data-ttu-id="bf973-526">获取的字符串。</span><span class="sxs-lookup"><span data-stu-id="bf973-526">Gets the string.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bf973-527">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf973-527">See also</span></span>

- <span data-ttu-id="bf973-528">[UCCollaborationLib](http://msdn.microsoft.com/library/UCCollaborationLib)命名空间</span><span class="sxs-lookup"><span data-stu-id="bf973-528">[UCCollaborationLib](http://msdn.microsoft.com/library/UCCollaborationLib) namespace</span></span> 
    

