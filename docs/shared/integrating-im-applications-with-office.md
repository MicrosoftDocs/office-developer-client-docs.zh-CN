---
title: 将 IM 应用程序与 Office 集成
manager: lindalu
ms.date: 12/03/2019
ms.audience: Developer
ms.assetid: beba316b-1dfe-4e1b-adae-42418906c177
description: 本文介绍如何配置即时消息 (IM) 客户端应用程序，以便它与 Office 2013 及更高版本中的社交功能集成，例如显示状态以及从联系人卡片发送即时消息等功能。
localization_priority: Priority
ms.openlocfilehash: c0094b880bae5cac2cef4236d3ff3edcefd21678
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819292"
---
# <a name="integrating-im-applications-with-office"></a><span data-ttu-id="5c84e-103">将 IM 应用程序与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="5c84e-103">Integrating IM applications with Office</span></span>

<span data-ttu-id="5c84e-104">本文介绍如何配置即时消息 (IM) 客户端应用程序，以便它与 Office 2013、Office 2016、Office 2019 和 Office 365 中的社交功能集成，例如显示状态以及从联系人卡片发送即时消息等功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-104">This article describes how to configure an instant message (IM) client application so that it integrates with the social features in Office 2013, including displaying presence and sending instant messages from the contact card.</span></span>
  
## <a name="introduction"></a><span data-ttu-id="5c84e-105">简介</span><span class="sxs-lookup"><span data-stu-id="5c84e-105">Introduction</span></span>
<span data-ttu-id="5c84e-106"><a name="off15_IMIntegration_Intro"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-106"></span></span>

<span data-ttu-id="5c84e-107">Office 2013（及更高版本）提供与 IM 客户端应用程序（包括 Lync 2013 和 Teams）的丰富集成功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-107">Office 2013 provides rich integration with IM client applications, including Lync 2013.</span></span> <span data-ttu-id="5c84e-108">此集成在 Word 2013、Excel、PowerPoint 2013、Outlook、Visio、Project 和 OneNote 中为用户提供了 IM 功能，并且在 SharePoint 页面上提供了状态集成。</span><span class="sxs-lookup"><span data-stu-id="5c84e-108">This integration provides users with IM capabilities from within Word 2013, Excel 2013, PowerPoint 2013, Outlook 2013, Visio 2013, Project 2013, and OneNote 2013 as well as providing presence integration on SharePoint 2013 pages.</span></span> <span data-ttu-id="5c84e-109">用户可查看其联系人列表中的联系人照片、姓名、当前状态和数据。</span><span class="sxs-lookup"><span data-stu-id="5c84e-109">Users can see the photo, name, presence status, and contact data for people in their contacts list.</span></span> <span data-ttu-id="5c84e-110">他们可直接从联系人卡片（Office 中显示联系信息和通信选项的 UI 元素）发起 IM 会话、视频通话或电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="5c84e-110">They can start an IM session, video call, or phone call directly from the contact card (the UI element in Office 2013 that surfaces contact information and communication options).</span></span> <span data-ttu-id="5c84e-111">借助 Office，无需退出电子邮件或文档即可轻松与联系人保持联系。</span><span class="sxs-lookup"><span data-stu-id="5c84e-111">Office 2013 makes it easy to stay connected to your contacts without taking you outside of your email or documents.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5c84e-112">本文使用术语 IM 客户端应用程序专门指代安装在与 IM 服务通信的用户计算机上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c84e-112">This article uses the term IM client application to refer specifically to the application installed on a user's computer that communicates to the IM service.</span></span> <span data-ttu-id="5c84e-113">例如，可将 Lync 2013 和 Teams 视为 IM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c84e-113">For example, Lync 2013 and Teams are considered an IM client applications.</span></span> <span data-ttu-id="5c84e-114">本文未提供有关 IM 客户端应用程序如何与 IM 服务进行通信或 IM 服务本身的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-114">This article does not provide details about how the IM client application communicates to the IM service or about the IM service itself.</span></span> 
  
<span data-ttu-id="5c84e-115">你可以自定义 IM 客户端应用程序，以便它与 Office 通信。</span><span class="sxs-lookup"><span data-stu-id="5c84e-115">You can customize an IM client application so that it communicates with Office.</span></span> <span data-ttu-id="5c84e-116">具体来说，你可以修改 IM 应用程序，以便在 Office UI 中显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="5c84e-116">Specifically, you can modify your IM application so that it displays the following information within the Office UI:</span></span>
  
- <span data-ttu-id="5c84e-117">联系人照片。</span><span class="sxs-lookup"><span data-stu-id="5c84e-117">Contact photo.</span></span>
    
- <span data-ttu-id="5c84e-118">联系人姓名。</span><span class="sxs-lookup"><span data-stu-id="5c84e-118">Contact name.</span></span>
    
- <span data-ttu-id="5c84e-119">联系人个人状态说明。</span><span class="sxs-lookup"><span data-stu-id="5c84e-119">Contact personal status note.</span></span>
    
- <span data-ttu-id="5c84e-120">联系人当前状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-120">Contact presence status.</span></span>
    
- <span data-ttu-id="5c84e-121">联系人状态字符串（例如“有空”或“外出”）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-121">Contact availability string (for example, "Available" or "Out of Office").</span></span>
    
- <span data-ttu-id="5c84e-122">联系人具有的功能字符串（例如“视频就绪”）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-122">Contact capability string (for example, "Video Ready").</span></span>
    
- <span data-ttu-id="5c84e-123">一键式 IM 启动。</span><span class="sxs-lookup"><span data-stu-id="5c84e-123">One-click IM launch.</span></span>
    
- <span data-ttu-id="5c84e-124">一键式视频呼叫启动。</span><span class="sxs-lookup"><span data-stu-id="5c84e-124">One-click video call launch.</span></span>
    
- <span data-ttu-id="5c84e-125">一键式电话呼叫启动（包括 SIP、电话号码、语音邮件和呼叫新号码）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-125">One-click phone call launch (including SIP, phone number, voice mail, and call new number).</span></span>
    
- <span data-ttu-id="5c84e-126">联系人管理（添加到 IM 组）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-126">Contact management (add to IM group).</span></span>
    
- <span data-ttu-id="5c84e-127">联系人位置和时区。</span><span class="sxs-lookup"><span data-stu-id="5c84e-127">Contact location and time zone.</span></span>
    
- <span data-ttu-id="5c84e-128">联系人数据、电话号码、电子邮件地址、职务和公司名称。</span><span class="sxs-lookup"><span data-stu-id="5c84e-128">Contact data, phone number, email address, title, and company name.</span></span>
    
<span data-ttu-id="5c84e-129">**图 1. Office 2013 中的联系人卡片**</span><span class="sxs-lookup"><span data-stu-id="5c84e-129">**Figure 1. Contact card in Office 2013**</span></span>

<span data-ttu-id="5c84e-130">![Office 2013 中的人员卡片](media/ocom15_peoplecard.png "Office 2013 中的人员卡片")</span><span class="sxs-lookup"><span data-stu-id="5c84e-130">![The People Card in Office 2013](media/ocom15_peoplecard.png "The People Card in Office 2013")</span></span>
  
<span data-ttu-id="5c84e-131">为了实现与 Office 的集成，IM 客户端应用程序必须实现由 Office 提供的一组接口才能连接到它。</span><span class="sxs-lookup"><span data-stu-id="5c84e-131">To enable this integration with Office, an IM client application must implement a set of interfaces that Office provides to connect to it.</span></span> <span data-ttu-id="5c84e-132">用于此集成的 API 包含在 Microsoft.Office.UC.dll 文件内的 [ UCCollborationLib ](https://docs.microsoft.com/previous-versions/office/communications/ff398475(v=ocs.14)) 命名空间中，该文件与包含 Lync/Skype for Business 的 Office 2013 版本安装在一起。</span><span class="sxs-lookup"><span data-stu-id="5c84e-132">The APIs for this integration are included in the [UCCollborationLib](https://docs.microsoft.com/previous-versions/office/communications/ff398475(v=ocs.14)) namespace that is contained in the Microsoft.Office.UC.dll file, which is installed with versions of Office 2013 that include Lync / Skype for Business.</span></span> <span data-ttu-id="5c84e-133">\*\* UCCollaborationLib \*\* 命名空间包含为与 Office 集成而必须实现的接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-133">The **UCCollaborationLib** namespace includes the interfaces that you must implement to integrate with Office.</span></span> 
  
> [!IMPORTANT] 
> <span data-ttu-id="5c84e-134">所需接口的类型库嵌入在 Lync 2013/Skype for Business 中。</span><span class="sxs-lookup"><span data-stu-id="5c84e-134">The type library for the required interfaces is embedded in Lync 2013/Skype for Business.</span></span> <span data-ttu-id="5c84e-135">对于第三方集成商，仅当目标计算机上安装了 Lync 2013 和 Skype for Business 时，此方法才有效。</span><span class="sxs-lookup"><span data-stu-id="5c84e-135">For third-party integrators, this works only when both Lync 2013 and Skype for Business are installed on the target machine.</span></span> <span data-ttu-id="5c84e-136">如果要使用 Office Standard 进行集成，则需要提取类型库并将其安装在目标计算机上。</span><span class="sxs-lookup"><span data-stu-id="5c84e-136">If you are integrating using Office Standard, you need to extract the type library and install it on the target machine.</span></span> <span data-ttu-id="5c84e-137">[Lync 2013 SDK](https://www.microsoft.com/download/details.aspx?id=36824) 包含 Microsoft.Office.UC.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="5c84e-137">The [Lync 2013 SDK](https://www.microsoft.com/download/details.aspx?id=36824) includes the Microsoft.Office.UC.dll file.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="5c84e-138">少数 Office 2010 应用程序可以与第三方 IM 提供商的应用程序进行类似的集成：Outlook 2010、Word 2010、Excel 2010、PowerPoint 2010 和 SharePoint Server 2010（使用 ActiveX 控件）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-138">A handful of Office 2010 applications can integrate similarly with a third-party IM provider application: Outlook 2010, Word 2010, Excel 2010, PowerPoint 2010, and SharePoint Server 2010 (using an ActiveX control).</span></span> <span data-ttu-id="5c84e-139">与 Office 2013 集成所需的许多步骤也适用于 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="5c84e-139">Many of the steps required for integration with Office 2013 apply to Office 2010 as well.</span></span> <span data-ttu-id="5c84e-140">Office 2010 与 IM 提供商的应用程序集成的方式有几个主要差异：</span><span class="sxs-lookup"><span data-stu-id="5c84e-140">There are several key differences in how Office 2010 integrates with an IM provider application:</span></span> 
>  - <span data-ttu-id="5c84e-141">Office 2010 不显示联系人的照片。</span><span class="sxs-lookup"><span data-stu-id="5c84e-141">Office 2010 does not display the contact's photo.</span></span> 
>  - <span data-ttu-id="5c84e-142">你必须单独从 Office 2010 下载 Microsoft.Office.Uc.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="5c84e-142">You must download the Microsoft.Office.Uc.dll file separately from Office 2010.</span></span> <span data-ttu-id="5c84e-143">[Lync 2010 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=18898) 包含适用于 Office 2010 的 Microsoft.Office.UC.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="5c84e-143">The [Lync 2010 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=18898) includes the Microsoft.Office.UC.dll file for Office 2010.</span></span> 
>  - <span data-ttu-id="5c84e-144">当 Office 应用程序在 IM 客户端应用程序上调用 [ IUCOfficeIntegration.GetAuthenticationInfo ](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) 方法时，它会传入字符串“14.0.0.0”。</span><span class="sxs-lookup"><span data-stu-id="5c84e-144">When the Office application calls the [IUCOfficeIntegration.GetAuthenticationInfo](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) method on the IM client application, it passes in the string "14.0.0.0".</span></span> 
>  - <span data-ttu-id="5c84e-145">Office 2010 一旦连接到 IM 客户端应用程序，就会枚举所有组和联系人。</span><span class="sxs-lookup"><span data-stu-id="5c84e-145">Office 2010 enumerates all groups and contacts as soon as it connects to an IM client application.</span></span> 
  
## <a name="how-office-integrates-with-an-im-client-application"></a><span data-ttu-id="5c84e-146">Office 如何与 IM 客户端应用程序集成</span><span class="sxs-lookup"><span data-stu-id="5c84e-146">How Office integrates with an IM client application</span></span>
<span data-ttu-id="5c84e-147"><a name="off15_IMIntegration_How"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-147"></span></span>

<span data-ttu-id="5c84e-148">当 Office 2013（或更高版本）应用程序启动时，它将完成以下流程，与默认 IM 客户端应用程序进行集成：</span><span class="sxs-lookup"><span data-stu-id="5c84e-148">When an Office 2013 application starts, it goes through the following process to integrate with the default IM client application:</span></span>
  
1. <span data-ttu-id="5c84e-149">检查注册表以发现默认的 IM 客户端应用程序，然后连接到它。</span><span class="sxs-lookup"><span data-stu-id="5c84e-149">It checks the registry to discover the default IM client application and then connects to it.</span></span>
    
2. <span data-ttu-id="5c84e-150">使用 IM 客户端应用程序进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5c84e-150">It authenticates with the IM client application.</span></span>
    
3. <span data-ttu-id="5c84e-151">连接到 IM 客户端应用程序公开的特定接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-151">It connects to specific interfaces that are exposed by the IM client application.</span></span>
    
4. <span data-ttu-id="5c84e-152">确定当前登录用户（本地用户）具有的功能，包括获取用户的联系人、确定用户的状态以及用户具有的 IM 功能（即时消息、视频聊天、VOIP 等）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-152">It determines the capabilities of the currently signed-in user (local user), including getting the user's contacts, determining the user's presence, and determining the user's IM capabilities (instant messaging, video chat, VOIP, and so on).</span></span>
    
5. <span data-ttu-id="5c84e-153">获取本地用户联系人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-153">It gets presence information for the local user's contacts.</span></span>
    
6. <span data-ttu-id="5c84e-154">当 IM 客户端应用程序关闭时，Office 应用程序将自动断开连接。</span><span class="sxs-lookup"><span data-stu-id="5c84e-154">When the IM client application shuts down, the Office 2013 application silently disconnects.</span></span>
    
### <a name="discovering-the-im-application"></a><span data-ttu-id="5c84e-155">发现 IM 应用程序</span><span class="sxs-lookup"><span data-stu-id="5c84e-155">Discovering the IM application</span></span>

<span data-ttu-id="5c84e-156">Office 应用程序会在注册表中查找几个特定的注册表项和条目，以便发现默认的 IM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c84e-156">The Office application looks for several specific keys and entries in the registry to discover the default IM client application.</span></span> <span data-ttu-id="5c84e-157">如果发现默认的 IM 客户端应用程序，它会尝试连接到它。</span><span class="sxs-lookup"><span data-stu-id="5c84e-157">If it discovers a default IM client application, it then attempts to connect to it.</span></span>
  
<span data-ttu-id="5c84e-158">Office 应用程序发现默认 IM 客户端应用程序的过程如下：</span><span class="sxs-lookup"><span data-stu-id="5c84e-158">The process that the Office application goes through to discover the default IM client application is as follows:</span></span>
  
1. <span data-ttu-id="5c84e-159">Office 应用程序会查看是否在注册表中设置了 HKEY_CURRENT_USER\Software\IM Providers\DefaultIMApp 子项，并读取其中列出的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="5c84e-159">The Office application looks to see if the HKEY_CURRENT_USER\Software\IM Providers\DefaultIMApp subkey in the registry is set and reads the application name listed there.</span></span>
    
2. <span data-ttu-id="5c84e-160">然后，Office 应用程序将读取 HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning 注册表项，并监视值更改。</span><span class="sxs-lookup"><span data-stu-id="5c84e-160">The Office application then reads the HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning key and monitors the value for changes.</span></span>
    
3. <span data-ttu-id="5c84e-161">Office 应用程序接下来会读取 HKEY_LOCAL_MACHINE\Software\IM Providers\ _Application name_ 注册表项，并获取存储在其中的 ProcessName 和 class ID (CLSID) 值。</span><span class="sxs-lookup"><span data-stu-id="5c84e-161">The Office application next reads the HKEY_LOCAL_MACHINE\Software\IM Providers\ _Application name_ registry key and gets the ProcessName and class ID (CLSID) values stored there.</span></span> 
    
4. <span data-ttu-id="5c84e-162">一旦 IM 客户端应用程序成功完成其启动序列并为状态集成正确注册所有类，它会将 HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning 注册表项设置为“2”，表示客户端应用程序正在运行。</span><span class="sxs-lookup"><span data-stu-id="5c84e-162">Once the IM client application has completed its start sequence successfully and registered all of the classes correctly for the presence integration, it sets the HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning key to "2", indicating that the client application is running.</span></span>
    
5. <span data-ttu-id="5c84e-163">当 Office 应用程序发现 HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning 注册表项已设置为“2”时，它会检查计算机上正在运行的进程列表以查找 IM 客户端应用程序的进程名称。</span><span class="sxs-lookup"><span data-stu-id="5c84e-163">When the Office application discovers that the HKEY_CURRENT_USER\Software\IM Providers\ _Application name_\UpAndRunning key has been set to "2", it checks the list of running processes on the computer for the process name of the IM client application.</span></span>
    
6. <span data-ttu-id="5c84e-164">在找到 IM 客户端应用程序使用的进程后，Office 应用程序将使用 CLSID 来调用 **CoCreateInstance**，以便与作为进程外 COM 服务器的 IM 客户端应用程序建立连接。</span><span class="sxs-lookup"><span data-stu-id="5c84e-164">Once the Office application finds the process that the IM client application uses, the Office application calls **CoCreateInstance** using the CLSID to establish a connection to the IM client application as an out-of-process COM server.</span></span> 
    
### <a name="authenticating-the-connection-to-the-im-application"></a><span data-ttu-id="5c84e-165">验证与 IM 应用程序的连接</span><span class="sxs-lookup"><span data-stu-id="5c84e-165">Authenticating the connection to the IM application</span></span>

<span data-ttu-id="5c84e-166">当 Office 应用程序与 IM 客户端应用程序建立连接后，它将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c84e-166">After the Office application establishes a connection to the IM client application, it then does the following:</span></span>
  
1. <span data-ttu-id="5c84e-167">Office 应用程序将调用 [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法来检查 [IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-167">The Office application calls [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method to check for the [IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) interface.</span></span> 
    
2. <span data-ttu-id="5c84e-168">然后，Office 应用程序将调用 **IUCOfficeIntegration.GetAuthenticationInfo** 方法，以便传入支持的最高集成版本（例如，“15.0.0.0”）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-168">The Office application then calls the **IUCOfficeIntegration.GetAuthenticationInfo** method, passing in the highest supported integration version (for example, "15.0.0.0").</span></span> 
    
3. <span data-ttu-id="5c84e-169">如果 IM 客户端应用程序支持作为参数传入的 Office 版本，则该应用程序会将以下硬编码的 XML 字符串返回给调用代码：</span><span class="sxs-lookup"><span data-stu-id="5c84e-169">If the IM client application supports the version of Office passed in as a parameter, the application returns the following hard-coded XML string to the calling code:</span></span>
    
    `<authenticationinfo>`
    
   > [!NOTE]
   > <span data-ttu-id="5c84e-170">由于遗留原因，如果 IM 客户端应用程序支持作为参数传入的 Office 版本，则必须将准确值 `<authenticationinfo>` 返回到对 \*\* GetAuthenticationInfo\*\* 的调用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-170">For legacy reasons, the IM client application must return the exact value  `<authenticationinfo>` to the call to **GetAuthenticationInfo** if it supports the version of Office passed in as a parameter.</span></span> 
  
4. <span data-ttu-id="5c84e-171">如果 IM 客户端应用程序无法返回值，则 Office 应用程序将重新使用下一个受支持的 Office 版本（例如，“14.0.0.0”）来调用 **GetAuthenticationInfo** 方法。</span><span class="sxs-lookup"><span data-stu-id="5c84e-171">If the IM client application fails to return a value, the Office application calls the **GetAuthenticationInfo** method again with the next highest supported version of Office (for example, "14.0.0.0").</span></span> 
    
5. <span data-ttu-id="5c84e-172">一旦 Office 确定 IM 客户端应用程序支持 IM 和状态集成，它就会连接到一组所需的接口以完成初始化。</span><span class="sxs-lookup"><span data-stu-id="5c84e-172">Once Office determines that the IM client application supports IM and presence integration, it connects to a required set of interfaces to finish initializing.</span></span> <span data-ttu-id="5c84e-173">（有关详细信息，请参阅[连接到所需的接口](#off15_IMIntegration_HowConnect)。）</span><span class="sxs-lookup"><span data-stu-id="5c84e-173">(For more information, see [Connecting to required interfaces](#off15_IMIntegration_HowConnect).)</span></span>
    
<span data-ttu-id="5c84e-174">如果 Office 应用程序在上述任何步骤中遇到错误，它将退出，并且在 Office 应用程序的会话期间不会再次建立状态集成。</span><span class="sxs-lookup"><span data-stu-id="5c84e-174">If the Office application encounters an error on any of the steps above, it backs out and presence integration is not established again during the session of the Office application.</span></span> 
  
### <a name="connecting-to-required-interfaces"></a><span data-ttu-id="5c84e-175">连接到所需的接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-175">Connecting to required interfaces</span></span>
<span data-ttu-id="5c84e-176"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-176"></span></span>

<span data-ttu-id="5c84e-177">在验证与 IM 客户端应用程序的连接后，Office 应用程序会尝试连接到 IM 客户端应用程序公开的一组必需接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-177">After authenticating the connection to the IM client application, the Office application attempts to connect to a set of required interfaces that the IM client application must expose.</span></span> <span data-ttu-id="5c84e-178">为此，Office 应用程序将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c84e-178">The Office application accomplishes this by doing the following:</span></span>
  
- <span data-ttu-id="5c84e-179">Office 应用程序将通过调用 **IUCOfficeIntegration.GetInterface** 方法来获取 [ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) 对象，以便从 [UCCollaborationLib.OIInterface](https://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) 枚举传入 **oiInterfaceLyncClient** 常量。</span><span class="sxs-lookup"><span data-stu-id="5c84e-179">The Office application gets an [ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) object by calling the **IUCOfficeIntegration.GetInterface** method, passing in the **oiInterfaceLyncClient** constant from the [UCCollaborationLib.OIInterface](https://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) enumeration.</span></span> 
    
- <span data-ttu-id="5c84e-180">Office 应用程序将通过调用 **IUCOfficeIntegration.GetInterface** 方法来获取 [IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation) 对象，以便从 **OIInterface** 枚举传入 **oiInterfaceAutomation** 常量。</span><span class="sxs-lookup"><span data-stu-id="5c84e-180">The Office application gets an [IAutomation](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation) object by calling the **IUCOfficeIntegration.GetInterface** method, passing in the **oiInterfaceAutomation** constant from the **OIInterface** enumeration.</span></span> 
    
- <span data-ttu-id="5c84e-181">Office 应用程序将设置 [_ILyncClientEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="5c84e-181">The Office application sets up the [_ILyncClientEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) event listener.</span></span> 
    
- <span data-ttu-id="5c84e-182">Office 应用程序将设置 [_IUCOfficeIntegrationEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) 事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="5c84e-182">The Office application sets up the [_IUCOfficeIntegrationEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) event listener.</span></span> 
    
- <span data-ttu-id="5c84e-183">Office 应用程序将通过访问 **ILyncClient.State** 属性从 IM 客户端应用程序获取登录状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-183">The Office application gets the sign-in state from the IM client application by accessing the **ILyncClient.State** property.</span></span> 
    
- <span data-ttu-id="5c84e-184">Office 应用程序将通过调用 **IUCOfficeIntegration.GetSupportedFeatures** 方法来获取 IM 客户端应用程序的功能，它将从 [UCCollaborationLib.OIFeature](https://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) 枚举返回一个标记。</span><span class="sxs-lookup"><span data-stu-id="5c84e-184">The Office application gets the capabilities of the IM client application by calling the **IUCOfficeIntegration.GetSupportedFeatures** method, which returns a flag from the [UCCollaborationLib.OIFeature](https://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) enumeration.</span></span> 
    
- <span data-ttu-id="5c84e-185">Office 应用程序将访问 **ILyncClient.Self** 属性以获取对 [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-185">The Office application accesses the **ILyncClient.Self** property to get a reference to an [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) object.</span></span> 
    
### <a name="retrieving-the-capabilities-of-the-local-user"></a><span data-ttu-id="5c84e-186">检索本地用户具有的功能</span><span class="sxs-lookup"><span data-stu-id="5c84e-186">Retrieving the capabilities of the local user</span></span>
<span data-ttu-id="5c84e-187"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-187"></span></span>

<span data-ttu-id="5c84e-188">Office 应用程序将通过执行以下操作来获取本地用户具有的功能：</span><span class="sxs-lookup"><span data-stu-id="5c84e-188">The Office application gets the capabilities of the local user by doing the following:</span></span>
  
1. <span data-ttu-id="5c84e-189">如果 IM 客户端应用程序支持 **IClient2** 接口，则 Office 会尝试通过访问 **IClient2.PrivateContactManager** 属性来获取 [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-189">If the IM client application supports the **IClient2** interface, Office tries to get an [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) object by accessing the **IClient2.PrivateContactManager** property.</span></span> 
    
2. <span data-ttu-id="5c84e-190">如果 IM 客户端应用程序不支持 **IClient2** 接口，则 Office 应用程序会尝试通过访问 **ILyncClient.ContactManager** 属性来获取 **IContactManager** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-190">If the IM application does not support the **IClient2** interface, Office application gets an **IContactManager** object by accessing the **ILyncClient.ContactManager** property.</span></span> <span data-ttu-id="5c84e-191">在建立任何其他 IM 功能之前，IM 客户端应用程序必须成功返回 **IContactManager** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-191">The IM client application must successfully return an **IContactManager** object before any other IM capabilities can be established.</span></span> 
    
3. <span data-ttu-id="5c84e-192">Office 应用程序将访问 **ILyncClient.Uri** 属性，然后调用 **IContactManager.GetContactByUri** 以获取与本地用户关联的 [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-192">The Office application accesses the **ILyncClient.Uri** property and then calls **IContactManager.GetContactByUri** to get the [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) object associated with the local user.</span></span> 
    
4. <span data-ttu-id="5c84e-193">然后，Office 应用程序将对 **IContact.CanStart** 进行多次调用以建立本地用户具有的功能，并依次传入 **ModalityTypes.ucModalityInstantMessage** 和 **ModalityTypes.ucModalityAudioVideo** 的值。</span><span class="sxs-lookup"><span data-stu-id="5c84e-193">The Office application then makes several calls to **IContact.CanStart** to establish the capabilities of the local user, passing in the values for **ModalityTypes.ucModalityInstantMessage** and **ModalityTypes.ucModalityAudioVideo** successively.</span></span> 
    
### <a name="retrieving-contact-presence"></a><span data-ttu-id="5c84e-194">检索联系人状态</span><span class="sxs-lookup"><span data-stu-id="5c84e-194">Retrieving contact presence</span></span>
<span data-ttu-id="5c84e-195"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-195"></span></span>

<span data-ttu-id="5c84e-196">Office 应用程序将通过执行以下操作获取联系人状态（包括本地用户）：</span><span class="sxs-lookup"><span data-stu-id="5c84e-196">The Office application gets contact presence, including the local user, by doing the following:</span></span> 
  
1. <span data-ttu-id="5c84e-197">Office 应用程序将调用 **IContact.GetContactInformation** 以从联系人获取状态项。</span><span class="sxs-lookup"><span data-stu-id="5c84e-197">The Office application calls **IContact.GetContactInformation** to get a presence item from the contact.</span></span> 
    
2. <span data-ttu-id="5c84e-198">然后，Office 应用程序会订阅联系人的状态更改。</span><span class="sxs-lookup"><span data-stu-id="5c84e-198">The Office application then subscribes to presence status changes from the contact.</span></span> <span data-ttu-id="5c84e-199">它通过调用 **IContactManager.CreateSubscription** 来获取 [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-199">It calls **IContactManager.CreateSubscription** to get an [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) object.</span></span> <span data-ttu-id="5c84e-200">它随后会调用 **IContactSubscription.AddContact**，以便将联系人添加到订阅中，然后调用 **IContactSubscription.Subscribe** 以更改联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-200">It then calls **IContactSubscription.AddContact** to add the contact to the subscription and then calls **IContactSubscription.Subscribe** to get changes in the contact's status.</span></span> 
    
3. <span data-ttu-id="5c84e-201">如果 IM 应用程序支持 **IContact2**，则 Office 将尝试通过调用 **IContact2.BatchGetContactInformation2** 来获取状态信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-201">If the IM application supports **IContact2**, Office attempts to get presence information by calling **IContact2.BatchGetContactInformation2**.</span></span>
    
4. <span data-ttu-id="5c84e-202">然后，Office 应用程序将通过调用 **IContact.BatchGetContactInformation** 来检索联系人的状态属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-202">The Office application then retrieves the presence properties for the contact by calling **IContact.BatchGetContactInformation**.</span></span> <span data-ttu-id="5c84e-203">Office 应用程序可以通过访问 **IContact.Settings** 属性来获取第二组状态属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-203">The Office application can get a second set of presence properties by accessing the **IContact.Settings** property.</span></span> 
    
5. <span data-ttu-id="5c84e-204">最后，Office 应用程序将通过访问 **IContact.CustomGroups** 属性来获取联系人的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="5c84e-204">Finally, the Office application gets the contact's group membership by accessing the **IContact.CustomGroups** property.</span></span> <span data-ttu-id="5c84e-205">这将返回 [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 集合，其中包含该联系人所属的所有 [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-205">This returns an [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) collection that includes all of the [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) objects that the contact belongs to.</span></span> 
    
### <a name="disconnecting-from-the-im-application"></a><span data-ttu-id="5c84e-206">断开与 IM 应用程序的连接</span><span class="sxs-lookup"><span data-stu-id="5c84e-206">Disconnecting from the IM application</span></span>
<span data-ttu-id="5c84e-207"><a name="off15_IMIntegration_HowConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-207"></span></span>

<span data-ttu-id="5c84e-208">当 Office 应用程序检测到来自 IM 应用程序的 **OnShuttingDown** 事件时，它将自动断开连接。</span><span class="sxs-lookup"><span data-stu-id="5c84e-208">When the Office 2013 application detects the **OnShuttingDown** event from the IM application, it disconnects silently.</span></span> <span data-ttu-id="5c84e-209">但是，如果 Office 应用程序在 IM 应用程序之前关闭，则 Office 应用程序无法保证已清除连接。</span><span class="sxs-lookup"><span data-stu-id="5c84e-209">However, if the Office application shuts down before the IM application, the Office application does not guarantee that the connection is cleaned up.</span></span> <span data-ttu-id="5c84e-210">IM 应用程序必须处理客户端连接泄漏。</span><span class="sxs-lookup"><span data-stu-id="5c84e-210">The IM application must handle client connection leaks.</span></span> 
  
## <a name="setting-registry-keys-and-entries"></a><span data-ttu-id="5c84e-211">设置注册表项</span><span class="sxs-lookup"><span data-stu-id="5c84e-211">Setting registry keys and entries</span></span>
<span data-ttu-id="5c84e-212"><a name="off15_IMIntegration_SetRegistry"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-212"></span></span>

<span data-ttu-id="5c84e-213">如前文所述，支持 IM 的 Office 应用程序会在注册表中查找特定的注册表项、条目和值，以便发现要连接的 IM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c84e-213">As mentioned previously, the IM-capable Office 2013 applications look for specific keys, entries, and values in the registry to discover the IM client application to connect to.</span></span> <span data-ttu-id="5c84e-214">这些注册表值为 Office 应用程序提供了类的进程名称和 CLSID，该类充当 IM 客户端应用程序的对象模型（即实现 **IUCOfficeIntegration** 接口的类）的入口点。</span><span class="sxs-lookup"><span data-stu-id="5c84e-214">These registry values provide the Office application with the process name and CLSID of the class that acts as the entry point to the IM client application's object model (that is, the class that implements the **IUCOfficeIntegration** interface).</span></span> <span data-ttu-id="5c84e-215">Office 应用程序将协同创建该类，并作为客户端连接到 IM 客户端应用程序中的进程外 COM 服务器。</span><span class="sxs-lookup"><span data-stu-id="5c84e-215">The Office application co-creates that class and connects as a client to the out-of-process COM server in the IM client application.</span></span> 
  
<span data-ttu-id="5c84e-216">使用表 1 标识必须在注册表中写入的注册表项、条目和值，以将 IM 客户端应用程序与 Office 集成。</span><span class="sxs-lookup"><span data-stu-id="5c84e-216">Use Table 1 to identify the keys, entries, and values that must be written in the registry to integrate an IM client application with Office.</span></span>
  
<span data-ttu-id="5c84e-217">**表 1. 用于设置默认 IM 客户端应用程序的注册表项**</span><span class="sxs-lookup"><span data-stu-id="5c84e-217">**Table 1. Registry keys for setting the default IM client application**</span></span>

|<span data-ttu-id="5c84e-218">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="5c84e-218">**Key**</span></span>|<span data-ttu-id="5c84e-219">**条目**</span><span class="sxs-lookup"><span data-stu-id="5c84e-219">**Entry**</span></span>|<span data-ttu-id="5c84e-220">**类型**</span><span class="sxs-lookup"><span data-stu-id="5c84e-220">**Type**</span></span>|<span data-ttu-id="5c84e-221">**值**</span><span class="sxs-lookup"><span data-stu-id="5c84e-221">**Value**</span></span>|<span data-ttu-id="5c84e-222">**示例**</span><span class="sxs-lookup"><span data-stu-id="5c84e-222">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5c84e-223">HKEY_LOCAL_MACHINE\Software\IM Providers\\<Application name\></span><span class="sxs-lookup"><span data-stu-id="5c84e-223">HKEY_LOCAL_MACHINE\Software\IM Providers\\<Application name\></span></span>  <br/> |<span data-ttu-id="5c84e-224">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="5c84e-224">FriendlyName</span></span>  <br/> |<span data-ttu-id="5c84e-225">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="5c84e-225">REG_SZ</span></span>  <br/> |<span data-ttu-id="5c84e-226">第三方 IM 客户端应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="5c84e-226">The name of the third-party IM client application.</span></span>  <br/> |<span data-ttu-id="5c84e-227">Litware IM 2012</span><span class="sxs-lookup"><span data-stu-id="5c84e-227">Litware IM 2012</span></span>  <br/> |
||<span data-ttu-id="5c84e-228">ProcessName</span><span class="sxs-lookup"><span data-stu-id="5c84e-228">ProcessName</span></span>  <br/> |<span data-ttu-id="5c84e-229">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="5c84e-229">REG_SZ</span></span>  <br/> |<span data-ttu-id="5c84e-230">第三方 IM 客户端应用程序的进程名称。</span><span class="sxs-lookup"><span data-stu-id="5c84e-230">The process name of the third-party IM client application.</span></span>  <br/> |<span data-ttu-id="5c84e-231">litware.exe</span><span class="sxs-lookup"><span data-stu-id="5c84e-231">litware.exe</span></span>  <br/> |
||<span data-ttu-id="5c84e-232">GUID</span><span class="sxs-lookup"><span data-stu-id="5c84e-232">GUID</span></span>  <br/> |<span data-ttu-id="5c84e-233">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="5c84e-233">REG_SZ</span></span>  <br/> |<span data-ttu-id="5c84e-234">IM 应用程序中可协同创建的根类的类 ID (CLSID)（实现 **IUCOfficeIntegration** 接口的类）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-234">A class ID (CLSID) for the root, cocreatable class in the IM application (the class that implements the **IUCOfficeIntegration** interface).</span></span>  <br/> |<span data-ttu-id="5c84e-235">(A GUID)</span><span class="sxs-lookup"><span data-stu-id="5c84e-235">(A GUID)</span></span>  <br/> |
|<span data-ttu-id="5c84e-236">HKEY_CURRENT_USER\Software\IM Providers</span><span class="sxs-lookup"><span data-stu-id="5c84e-236">HKEY_CURRENT_USER\Software\IM Providers</span></span>  <br/> |<span data-ttu-id="5c84e-237">DefaultIMApp</span><span class="sxs-lookup"><span data-stu-id="5c84e-237">DefaultIMApp</span></span>  <br/> |<span data-ttu-id="5c84e-238">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="5c84e-238">REG_SZ</span></span>  <br/> |<span data-ttu-id="5c84e-239">IM 客户端应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="5c84e-239">The name of the IM client application.</span></span> <span data-ttu-id="5c84e-240">它必须与 HKEY_LOCAL_MACHINE 中的顶层注册表项 (hive) 上的名称相同。</span><span class="sxs-lookup"><span data-stu-id="5c84e-240">This must be the same as the name at the top-level registry key (hive) in the HKEY_LOCAL_MACHINE.</span></span>  <br/> |<span data-ttu-id="5c84e-241">Litware</span><span class="sxs-lookup"><span data-stu-id="5c84e-241">Litware</span></span>  <br/> |
|<span data-ttu-id="5c84e-242">HKEY_CURRENT_USER\Software\IM Providers\\<Application name\></span><span class="sxs-lookup"><span data-stu-id="5c84e-242">HKEY_CURRENT_USER\Software\IM Providers\\<Application name\></span></span>  <br/> |<span data-ttu-id="5c84e-243">UpAndRunning</span><span class="sxs-lookup"><span data-stu-id="5c84e-243">UpAndRunning</span></span>  <br/> |<span data-ttu-id="5c84e-244">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="5c84e-244">REG_DWORD</span></span>  <br/> | <span data-ttu-id="5c84e-245">0 到 2 之间的整数值：</span><span class="sxs-lookup"><span data-stu-id="5c84e-245">An integer value between 0 and 2:</span></span>  <br/>  <span data-ttu-id="5c84e-246">0—未运行</span><span class="sxs-lookup"><span data-stu-id="5c84e-246">0—Not running</span></span>  <br/>  <span data-ttu-id="5c84e-247">1—正在启动</span><span class="sxs-lookup"><span data-stu-id="5c84e-247">1—Starting</span></span>  <br/>  <span data-ttu-id="5c84e-248">2—正在运行</span><span class="sxs-lookup"><span data-stu-id="5c84e-248">2—Running</span></span>  <br/> <br/><span data-ttu-id="5c84e-249">**注释**：应用程序名称注册表项必须与 DefaultIMApp 条目的值相同。</span><span class="sxs-lookup"><span data-stu-id="5c84e-249">**NOTE**:  The application name registry key must be the same as the value of the DefaultIMApp entry.</span></span>           ||
   
## <a name="implementing-the-required-interfaces-for-integration-with-office"></a><span data-ttu-id="5c84e-250">实现与 Office 集成所需的接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-250">Implementing the required interfaces for integration with Office</span></span>
<span data-ttu-id="5c84e-251"><a name="off15_IMIntegration_ImplementRequired"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-251"></span></span>

<span data-ttu-id="5c84e-252">**UCCollaborationLib** 命名空间有三个接口，IM 客户端应用程序的可执行文件（或 COM 服务器）必须实现这些接口，这样才能与 Office 集成。</span><span class="sxs-lookup"><span data-stu-id="5c84e-252">There are three interfaces from the **UCCollaborationLib** namespace that the executable (or COM server) of an IM client application must implement so that it can integrate with Office.</span></span> <span data-ttu-id="5c84e-253">如果未实现这些接口，则 Office 应用程序将在初始化过程中退出，并且不会与 IM 客户端应用程序建立连接。</span><span class="sxs-lookup"><span data-stu-id="5c84e-253">If these interfaces are not implemented, the Office application backs out during the initialization process and the connection with the IM client application is not established.</span></span> 
  
<span data-ttu-id="5c84e-254">所需的接口如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c84e-254">The required interfaces are as follows:</span></span>
  
- <span data-ttu-id="5c84e-255">[IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration) — 虽然不是必需的，但是 **_IUCOfficeIntegrationEvents** 接口也应该在同一个派生类中实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-255">[IUCOfficeIntegration](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IUCOfficeIntegration)—Although not required, the **_IUCOfficeIntegrationEvents** interface should also be implemented in the same derived class.</span></span> 
    
- <span data-ttu-id="5c84e-256">[ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient) — 虽然不是必需的，但是 **_ILyncClientEvents** 接口也应该在同一个派生类中实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-256">[ILyncClient](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILyncClient)—Although not required, the **_ILyncClientEvents** interface should also be implemented in the same derived class.</span></span> 
    
- [<span data-ttu-id="5c84e-257">IAutomation</span><span class="sxs-lookup"><span data-stu-id="5c84e-257">IAutomation</span></span>](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IAutomation)
    
### <a name="iucofficeintegration-interface"></a><span data-ttu-id="5c84e-258">IUCOfficeIntegration 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-258">IUCOfficeIntegration interface</span></span>
<span data-ttu-id="5c84e-259"><a name="off15_IMIntegration_ImplementRequired_IUCOfficeIntegration"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-259"></span></span>

<span data-ttu-id="5c84e-260">**IUCOfficeIntegration** 接口提供用于将 Office 应用程序连接到 IM 客户端应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="5c84e-260">The **IUCOfficeIntegration** interface provides the entry-point for an Office application to connect to the IM client application.</span></span> <span data-ttu-id="5c84e-261">作为启动与 IM 客户端应用程序进行连接的过程的一部分。该接口定义了 Office 应用程序调用的三种方法。</span><span class="sxs-lookup"><span data-stu-id="5c84e-261">The interface defines three methods that an Office application calls as part of the process of initiating a connection with the IM client application.</span></span> <span data-ttu-id="5c84e-262">实现 **IUCOfficeIntegration** 接口的类必须是可协同创建的类，这样 Office 才能协同创建它的实例。</span><span class="sxs-lookup"><span data-stu-id="5c84e-262">The class that implements the **IUCOfficeIntegration** interface must be co-creatable so that Office can co-create an instance of it.</span></span> <span data-ttu-id="5c84e-263">此外，它还必须公开在 HKEY_LOCAL_MACHINE\Software\IM Providers\  _Application name_ 注册表项中作为 GUID 条目值输入的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="5c84e-263">In addition, it must expose the CLSID that is entered as the value for the GUID entry in the HKEY_LOCAL_MACHINE\Software\IM Providers\  _Application name_ registry key.</span></span> 
  
<span data-ttu-id="5c84e-264">从 **IUCOfficeIntegration** 继承的类也应该实现 **_IUCOfficeIntegrationEvents** 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-264">The class that inherits from **IUCOfficeIntegration** should also implement the **_IUCOfficeIntegrationEvents** interface.</span></span> <span data-ttu-id="5c84e-265">**_IUCOfficeIntegrationEvents** 接口包含用于公开 **IUCOfficeIntegration** 接口的事件处理程序的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-265">The **_IUCOfficeIntegrationEvents** interface contains the members that expose the event handlers of the **IUCOfficeIntegration** interface.</span></span> 
  
<span data-ttu-id="5c84e-266">表 2 显示必须在继承自 **IUCOfficeIntegration** 和 **_IUCOfficeIntegration** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-266">Table 2 shows the members that must be implemented in the class that inherits from **IUCOfficeIntegration** and **_IUCOfficeIntegration**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-267">有关 **IUCOfficeIntegration** 和 **_IUCOfficeIntegrationEvents** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IUCOfficeIntegration](https://msdn.microsoft.com/library/UCCollaborationLib.IUCOfficeIntegration) 和 [UCCollaborationLib._IUCOfficeIntegrationEvents](https://msdn.microsoft.com/library/UCCollaborationLib._IUCOfficeIntegrationEvents)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-267">For more information about the **IUCOfficeIntegration** and **_IUCOfficeIntegrationEvents** interfaces and their members, see [UCCollaborationLib.IUCOfficeIntegration](https://msdn.microsoft.com/library/UCCollaborationLib.IUCOfficeIntegration) and [UCCollaborationLib._IUCOfficeIntegrationEvents](https://msdn.microsoft.com/library/UCCollaborationLib._IUCOfficeIntegrationEvents).</span></span> 
  
<span data-ttu-id="5c84e-268">**表 2. IUCOfficeIntegration 和 _IUCOfficeIntegrationEvents 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-268">**Table 2. Implementation of the IUCOfficeIntegration and _IUCOfficeIntegrationEvents interfaces**</span></span>

|<span data-ttu-id="5c84e-269">**接口**</span><span class="sxs-lookup"><span data-stu-id="5c84e-269">**Interface**</span></span>|<span data-ttu-id="5c84e-270">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-270">**Member**</span></span>|<span data-ttu-id="5c84e-271">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-271">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c84e-272">**IUCOfficeIntegration**</span><span class="sxs-lookup"><span data-stu-id="5c84e-272">**IUCOfficeIntegration**</span></span> <br/> |<span data-ttu-id="5c84e-273">**GetAuthenticationInfo** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-273">**GetAuthenticationInfo** method</span></span>  <br/> |<span data-ttu-id="5c84e-274">获取身份验证信息字符串。</span><span class="sxs-lookup"><span data-stu-id="5c84e-274">Gets the authentication info string.</span></span>  <br/> |
||<span data-ttu-id="5c84e-275">**GetInterface** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-275">**GetInterface** method</span></span>  <br/> |<span data-ttu-id="5c84e-276">获取特定版本的接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-276">Gets the interface of a particular version.</span></span>  <br/> |
||<span data-ttu-id="5c84e-277">**GetSupportedFeatures** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-277">**GetSupportedFeatures** method</span></span>  <br/> |<span data-ttu-id="5c84e-278">获取受支持的 Office 集成功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-278">Gets the supported Office integration features.</span></span>  <br/> |
|<span data-ttu-id="5c84e-279">**_IUCOfficeIntegrationEvents**</span><span class="sxs-lookup"><span data-stu-id="5c84e-279">**_IUCOfficeIntegrationEvents**</span></span> <br/> |<span data-ttu-id="5c84e-280">**OnShuttingDown** 事件</span><span class="sxs-lookup"><span data-stu-id="5c84e-280">**OnShuttingDown** event</span></span>  <br/> |<span data-ttu-id="5c84e-281">当 IM 客户端应用程序尝试关闭时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="5c84e-281">The event raised when the IM client application is trying to shut down.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-282">使用以下代码定义从 IM 客户端应用程序中的 **IUCOfficeIntegration** 和 **_IUCOfficeIntegration** 接口继承的类。</span><span class="sxs-lookup"><span data-stu-id="5c84e-282">Use the following code to define a class that inherits from the **IUCOfficeIntegration** and **_IUCOfficeIntegration** interfaces within an IM client application.</span></span> 
  
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

<span data-ttu-id="5c84e-283">**GetAuthenticationInfo** 方法将字符串作为 _version_ 参数的自变量。</span><span class="sxs-lookup"><span data-stu-id="5c84e-283">The **GetAuthenticationInfo** method takes a string as an argument for the  _version_ parameter.</span></span> <span data-ttu-id="5c84e-284">当 Office 应用程序调用此方法时，它会传入自变量的两个字符串之一，具体取决于 Office 的版本。</span><span class="sxs-lookup"><span data-stu-id="5c84e-284">When the Office application calls this method, it passes in one of two strings for the argument, depending on the version of Office.</span></span> <span data-ttu-id="5c84e-285">当 Office 应用程序为该方法提供 IM 客户端应用程序支持的 Office 版本（即支持该功能）时，**GetAuthenticationInfo** 方法将返回硬编码的 XML 字符串`<authenticationinfo>`。</span><span class="sxs-lookup"><span data-stu-id="5c84e-285">When the Office application supplies the method with the version of Office that the IM client application supports (that is, supports the functionality), the **GetAuthenticationInfo** method returns a hard-coded XML string `<authenticationinfo>`.</span></span> 
  
<span data-ttu-id="5c84e-286">使用以下代码在 IM 客户端应用程序代码中实现 **GetAuthentication** 方法。</span><span class="sxs-lookup"><span data-stu-id="5c84e-286">Use the following code to implement the **GetAuthentication** method within the IM client application code.</span></span> 
  
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

<span data-ttu-id="5c84e-287">**GetInterface** 方法会将对类的引用传递给调用代码，具体取决于作为 _interface_ 参数的自变量传入的内容。</span><span class="sxs-lookup"><span data-stu-id="5c84e-287">The **GetInterface** method shuttles references to classes to the calling code, depending on what is passed in as an argument for the  _interface_ parameter.</span></span> <span data-ttu-id="5c84e-288">当 Office 应用程序调用 **GetInterface** 方法时，它会传入接口参数的两个值之一：[UCCollaborationLib.OIInterface](https://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) 枚举的 **oiInterfaceILyncClient** 常量 (1) 或 **oiInterfaceIAutomation** 常量 (2)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-288">When an Office application calls the **GetInterface** method, it passes in one of two values for the interface parameter: either the **oiInterfaceILyncClient** constant (1) or the **oiInterfaceIAutomation** constant (2) of the [UCCollaborationLib.OIInterface](https://msdn.microsoft.com/library/UCCollaborationLib.OIInterface) enumeration.</span></span> <span data-ttu-id="5c84e-289">如果 Office 应用程序传入 **oiInterfaceILyncClient** 常量，则 **GetInterface** 方法将返回对实现 **ILyncClient** 接口的类的引用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-289">If the Office application passes in the **oiInterfaceILyncClient** constant, the **GetInterface** method returns a reference to a class that implements the **ILyncClient** interface.</span></span> <span data-ttu-id="5c84e-290">如果 Office 应用程序传入 **oiInterfaceIAutomation** 常量，则 **GetInterface** 方法将返回对实现 **IAutomation** 接口的类的引用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-290">If the Office application passes in the **oiInterfaceIAutomation** constant, the **GetInterface** method returns a class that implements the **IAutomation** interface.</span></span> 
  
<span data-ttu-id="5c84e-291">使用以下代码示例在 IM 客户端应用程序代码中实现 **GetInterface** 方法。</span><span class="sxs-lookup"><span data-stu-id="5c84e-291">Use the following code example to implement the **GetInterface** method within the IM client application code.</span></span> 
  
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

<span data-ttu-id="5c84e-292">**GetSupportedFeatures** 方法返回有关 IM 客户端应用程序支持的 IM 功能的信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-292">The **GetSupportedFeatures** method returns information about the IM features that the IM client application supports.</span></span> <span data-ttu-id="5c84e-293">它为其唯一参数 _version_ 使用字符串。</span><span class="sxs-lookup"><span data-stu-id="5c84e-293">It takes a string for its only parameter,  _version_.</span></span> <span data-ttu-id="5c84e-294">当 Office 应用程序调用 **GetSupportedFeatures** 方法时，该方法将返回 [UCCollaborationLib.OIFeature](https://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="5c84e-294">When the Office application calls the **GetSupportFeatures** method, the method returns a value from the [UCCollaborationLib.OIFeature](https://msdn.microsoft.com/library/UCCollaborationLib.OIFeature) enumeration.</span></span> <span data-ttu-id="5c84e-295">返回的值用于指定 IM 客户端的功能，系统通过向此值添加标记，为 IM 应用程序指明 IM 客户端应用程序的每项功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-295">The returned value specifies the capabilities of the IM client, where each capability of the IM client application is indicated to the Office application by adding a flag to the value.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="5c84e-296">Office 2013（或更高版本）应用程序将忽略 **OIFeature** 枚举中的以下常量：</span><span class="sxs-lookup"><span data-stu-id="5c84e-296">Office 2013 applications ignore the following constants in the **OIFeature** enumeration:</span></span> 
> - <span data-ttu-id="5c84e-297">**oiFeaturePictures** (2)</span><span class="sxs-lookup"><span data-stu-id="5c84e-297">**oiFeaturePictures** (2)</span></span> 
> - <span data-ttu-id="5c84e-298">**oiFeatureFreeBusyIntegration**</span><span class="sxs-lookup"><span data-stu-id="5c84e-298">**oiFeatureFreeBusyIntegration**</span></span>
> - <span data-ttu-id="5c84e-299">**oiFeaturePhoneNormalization**</span><span class="sxs-lookup"><span data-stu-id="5c84e-299">**oiFeaturePhoneNormalization**</span></span>
  
<span data-ttu-id="5c84e-300">使用以下代码示例在 IM 客户端应用程序代码中实现 **GetSupportFeatures** 方法。</span><span class="sxs-lookup"><span data-stu-id="5c84e-300">Use the following code example to implement the **GetSupportFeatures** method within the IM client application code.</span></span> 
  
```cs
public OIFeature GetSupportedFeatures(string _version)
{
    OIFeature supportedFeature1 = OIFeature.oiFeatureQuickContacts;
    OIFeature supportedFeature2 = OIFeature.oiFeatureFastSearch;
    return (supportedFeature1 | supportedFeature2);
}

```

### <a name="ilyncclient-interface"></a><span data-ttu-id="5c84e-301">ILyncClient 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-301">ILyncClient interface</span></span>
<span data-ttu-id="5c84e-302"><a name="off15_IMIntegration_ImplementRequired_ILyncClient"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-302"></span></span>

<span data-ttu-id="5c84e-303">**ILyncClient** 接口将映射到 IM 客户端应用程序本身的功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-303">The **ILyncClient** interface maps to the capabilities of the IM client application itself.</span></span> <span data-ttu-id="5c84e-304">它公开了引用登录到应用程序的用户（即本地用户，由 [UCCollaborationLib.ISelf](https://msdn.microsoft.com/library/UCCollaborationLib.ISelf) 接口表示）的属性、应用程序的状态、本地用户的联系人列表以及某些其他设置。</span><span class="sxs-lookup"><span data-stu-id="5c84e-304">It exposes properties that refer to the person who is signed into the application (the local user, represented by the [UCCollaborationLib.ISelf](https://msdn.microsoft.com/library/UCCollaborationLib.ISelf) interface), the state of the application, the list of contacts for the local user, and several other settings.</span></span> <span data-ttu-id="5c84e-305">当它尝试连接到 IM 客户端应用程序时，Office 应用程序会获取对实现 **ILyncClient** 接口的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-305">When it's trying to connect to the IM client application, the Office application gets a reference to an object that implements the **ILyncClient** interface.</span></span> <span data-ttu-id="5c84e-306">Office 可以从该引用中访问 IM 客户端应用程序的大部分功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-306">From that reference, Office can access much of the functionality of the IM client application.</span></span> 
  
<span data-ttu-id="5c84e-307">此外，实现 **ILyncClient** 接口的类还应实现 **_ILyncClientEvents** 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-307">In addition, the class that implements the **ILyncClient** interface should also implement the **_ILyncClientEvents** interface.</span></span> <span data-ttu-id="5c84e-308">**_ILyncClientEvents** 接口公开了监视 IM 客户端应用程序状态所需的几个事件。</span><span class="sxs-lookup"><span data-stu-id="5c84e-308">The **_ILyncClientEvents** interface exposes several of the events that are required for monitoring the state of the IM client application.</span></span> 
  
<span data-ttu-id="5c84e-309">表 3 显示必须在继承自 **ILyncClient** 和 **_ILyncClientEvents** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-309">Table 3 shows the members that must be implemented in the class that inherits from **ILyncClient** and **_ILyncClientEvents**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-310">表中未列出的 **ILyncClient** 或 **\_ILyncClientEvents** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-310">Any member of the **ILyncClient** or **\_ILyncClientEvents** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-311">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E\_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-311">Members that are present but not implemented can throw a **NotImplementedException** or **E\_NOTIMPL** error.</span></span> 
> 
> <span data-ttu-id="5c84e-312">有关 **ILyncClient** 和 **_ILyncClientEvents** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.ILyncClient](https://msdn.microsoft.com/library/UCCollaborationLib.ILyncClient) 和 [UCCollaborationLib._ILyncClientEvents](https://msdn.microsoft.com/library/UCCollaborationLib._ILyncClientEvents)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-312">For more information about the **ILyncClient** and **_ILyncClientEvents** interfaces and their members, see [UCCollaborationLib.ILyncClient](https://msdn.microsoft.com/library/UCCollaborationLib.ILyncClient) and [UCCollaborationLib._ILyncClientEvents](https://msdn.microsoft.com/library/UCCollaborationLib._ILyncClientEvents).</span></span> 
  
<span data-ttu-id="5c84e-313">**表 3. ILyncClient 和 ILyncClientEvents 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-313">**Table 3. Implementation of ILyncClient and ILyncClientEvents interfaces**</span></span>

|<span data-ttu-id="5c84e-314">**接口**</span><span class="sxs-lookup"><span data-stu-id="5c84e-314">**Interface**</span></span>|<span data-ttu-id="5c84e-315">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-315">**Member**</span></span>|<span data-ttu-id="5c84e-316">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-316">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c84e-317">**ILyncClient**</span><span class="sxs-lookup"><span data-stu-id="5c84e-317">**ILyncClient**</span></span> <br/> |<span data-ttu-id="5c84e-318">**ContactManager** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-318">**ContactManager** property</span></span>  <br/> |<span data-ttu-id="5c84e-319">获取联系人组管理器。</span><span class="sxs-lookup"><span data-stu-id="5c84e-319">Gets the contact group manager.</span></span>  <br/> |
||<span data-ttu-id="5c84e-320">**ConversationManager** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-320">**ConversationManager** property</span></span>  <br/> |<span data-ttu-id="5c84e-321">获取对话管理器。</span><span class="sxs-lookup"><span data-stu-id="5c84e-321">Gets the conversations manager.</span></span>  <br/> |
||<span data-ttu-id="5c84e-322">**Self** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-322">**Self** property</span></span>  <br/> |<span data-ttu-id="5c84e-323">获取 **Self** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-323">Gets the **Self** object.</span></span>  <br/> |
||<span data-ttu-id="5c84e-324">**SignIn** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-324">**SignIn** method</span></span>  <br/> |<span data-ttu-id="5c84e-325">以特定状态启动 IM 客户端应用程序登录过程。</span><span class="sxs-lookup"><span data-stu-id="5c84e-325">Starts the IM client application sign-in process with a specific availability.</span></span>  <br/> |
||<span data-ttu-id="5c84e-326">**State** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-326">**State** property</span></span>  <br/> |<span data-ttu-id="5c84e-327">获取当前平台状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-327">Gets the current platform state.</span></span>  <br/> |
||<span data-ttu-id="5c84e-328">**Uri** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-328">**Uri** property</span></span>  <br/> |<span data-ttu-id="5c84e-329">获取 IM 客户端应用程序的 URI。</span><span class="sxs-lookup"><span data-stu-id="5c84e-329">Gets the URI of the IM client application.</span></span>  <br/> |
|<span data-ttu-id="5c84e-330">**_ILyncClientEvents**</span><span class="sxs-lookup"><span data-stu-id="5c84e-330">**_ILyncClientEvents**</span></span> <br/> |<span data-ttu-id="5c84e-331">**OnStateChanged** 事件</span><span class="sxs-lookup"><span data-stu-id="5c84e-331">**OnStateChanged** event</span></span>  <br/> |<span data-ttu-id="5c84e-332">当 IM 客户端应用程序状态更改时引发。</span><span class="sxs-lookup"><span data-stu-id="5c84e-332">Raised when the IM client application state changes.</span></span> <span data-ttu-id="5c84e-333">你应该处理此事件并获取 **eventData.NewState** 属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-333">You should handle this event and get the **eventData.NewState** property.</span></span> <span data-ttu-id="5c84e-334">当应用程序中的任何子系统导致状态更改时，将为绑定到 IM 客户端应用程序实例的所有进程引发该事件。</span><span class="sxs-lookup"><span data-stu-id="5c84e-334">The event is raised for all processes bound to an instance of an IM client application when any subsystem in the application causes the state change.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-335">在初始化过程中，Office 将访问 **ILyncClient.State** 属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-335">During the initialization process, Office accesses the **ILyncClient.State** property.</span></span> <span data-ttu-id="5c84e-336">此属性需要从 [UCCollaborationLib.ClientState](https://msdn.microsoft.com/library/UCCollaborationLib.ClientState) 枚举中返回一个值。</span><span class="sxs-lookup"><span data-stu-id="5c84e-336">This property needs to return a value from the [UCCollaborationLib.ClientState](https://msdn.microsoft.com/library/UCCollaborationLib.ClientState) enumeration.</span></span> 
  
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

<span data-ttu-id="5c84e-337">**State** 属性用于存储 IM 客户端应用程序的当前状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-337">The **State** property stores the current status of the IM client application.</span></span> <span data-ttu-id="5c84e-338">必须在整个 IM 客户端应用程序会话中设置和更新它。</span><span class="sxs-lookup"><span data-stu-id="5c84e-338">It must be set and updated throughout the IM client application session.</span></span> <span data-ttu-id="5c84e-339">当 IM 客户端应用程序登录、注销或关闭时，应设置 **State** 属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-339">When the IM client application signs in, signs out, or shuts down, it should set the **State** property.</span></span> <span data-ttu-id="5c84e-340">最好在 **ILyncClient.SignIn** 和 **ILyncClient.SignOut** 方法中设置此属性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5c84e-340">It is best to set this property within the **ILyncClient.SignIn** and **ILyncClient.SignOut** methods, as the following example demonstrates.</span></span> 
  
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

<span data-ttu-id="5c84e-341">以下代码示例演示如何使用 **_ILyncClientEvents** 和 **_IUCOfficeIntegrationEvents** 接口设置事件侦听器。</span><span class="sxs-lookup"><span data-stu-id="5c84e-341">The following code example demonstrates how to set up the event listener using the _ **ILyncClientEvents** and _ **IUCOfficeIntegrationEvents** interfaces.</span></span> 
  
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

### <a name="iautomation-interface"></a><span data-ttu-id="5c84e-342">IAutomation 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-342">IAutomation interface</span></span>
<span data-ttu-id="5c84e-343"><a name="off15_IMIntegration_ImplementRequired_IAutomation"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-343"></span></span>

<span data-ttu-id="5c84e-344">**IAutomation** 接口用于自动化 IM 客户端应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-344">The **IAutomation** interface automates features of the IM client application.</span></span> <span data-ttu-id="5c84e-345">它可用于启动对话、加入会议以及提供可扩展性窗口上下文。</span><span class="sxs-lookup"><span data-stu-id="5c84e-345">It can be used to start conversations, join conferences, and provide extensibility window context.</span></span> 
  
<span data-ttu-id="5c84e-346">表 4 显示必须在继承自 **IAutomation** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-346">Table 4 shows the members that must be implemented in the class that inherits from **IAutomation**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-347">表中未列出的 **IAutomation** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-347">Any member of the **IAutomation** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-348">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-348">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
> 
> <span data-ttu-id="5c84e-349">有关 **IAutomation** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IAutomation](https://msdn.microsoft.com/library/UCCollaborationLib.IAutomation)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-349">For more information about the **IAutomation** interface and its members, see [UCCollaborationLib.IAutomation](https://msdn.microsoft.com/library/UCCollaborationLib.IAutomation).</span></span> 
  
<span data-ttu-id="5c84e-350">**表 4. IAutomation 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-350">**Table 4. Implementation of IAutomation interface**</span></span>

|<span data-ttu-id="5c84e-351">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-351">**Member**</span></span>|<span data-ttu-id="5c84e-352">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-352">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84e-353">**StartConversation** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-353">**StartConversation** method</span></span>  <br/> |<span data-ttu-id="5c84e-354">使用指定的对话模态启动对话。</span><span class="sxs-lookup"><span data-stu-id="5c84e-354">Starts a conversation using the specified conversation modality.</span></span> <span data-ttu-id="5c84e-355">将返回 **IConversationWindow** 的实例。</span><span class="sxs-lookup"><span data-stu-id="5c84e-355">An instance of **IConversationWindow** is returned.</span></span>  <br/> |
   
## <a name="implementing-contact-presence-integration"></a><span data-ttu-id="5c84e-356">实现联系人状态集成</span><span class="sxs-lookup"><span data-stu-id="5c84e-356">Implementing contact presence integration</span></span>
<span data-ttu-id="5c84e-357"><a name="off15_IMIntegration_ImplementIMFeatures"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-357"></span></span>

<span data-ttu-id="5c84e-358">除了前面讨论的三个必需接口之外，还有一些其他接口对于在 Office 中启用联系人状态功能非常重要。</span><span class="sxs-lookup"><span data-stu-id="5c84e-358">In addition to the three required interfaces discussed previously, there are several other interfaces that are important for enabling contact presence functionality in Office.</span></span> <span data-ttu-id="5c84e-359">其中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="5c84e-359">These include the following:</span></span>
  
- <span data-ttu-id="5c84e-360">[IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) 或 **IContact2** 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-360">The [IContact](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContact) or **IContact2** interface.</span></span> 
    
- <span data-ttu-id="5c84e-361">[ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-361">The [ISelf](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ISelf) interface.</span></span> 
    
- <span data-ttu-id="5c84e-362">[IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) 和 [_IContactManagerEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-362">The [IContactManager](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) and [_IContactManagerEvents](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactManager) interfaces.</span></span> 
    
- <span data-ttu-id="5c84e-363">[IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 和 [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-363">The [IGroup](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) and [IGroupCollection](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IGroup) interfaces.</span></span> 
    
- <span data-ttu-id="5c84e-364">[IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-364">The [IContactSubscription](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactSubscription) interface.</span></span> 
    
- <span data-ttu-id="5c84e-365">[IContactEndPoint](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactEndPoint) 接口。</span><span class="sxs-lookup"><span data-stu-id="5c84e-365">The [IContactEndPoint](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_IContactEndPoint) interface.</span></span> 
    
- <span data-ttu-id="5c84e-366">[ILocaleString](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILocaleString) 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-366">The [ILocaleString](integrating-im-applications-with-office.md#off15_IMIntegration_ImplementRequired_ILocaleString) interface</span></span> 
    
### <a name="icontact-interface"></a><span data-ttu-id="5c84e-367">IContact 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-367">IContact interface</span></span>
<span data-ttu-id="5c84e-368"><a name="off15_IMIntegration_ImplementRequired_IContact"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-368"></span></span>

<span data-ttu-id="5c84e-369">**IContact** 接口表示 IM 客户端应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="5c84e-369">The **IContact** interface represents an IM client application user.</span></span> <span data-ttu-id="5c84e-370">该接口将公开用户的状态、可用模态、组成员资格和联系人类型属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-370">The interface exposes presence, available modalities, group membership, and contact type properties for a user.</span></span> <span data-ttu-id="5c84e-371">要与其他用户开始对话，你必须提供 **IContact** 的用户实例。</span><span class="sxs-lookup"><span data-stu-id="5c84e-371">To start a conversation with another user, you must provide that user instance of **IContact**.</span></span>
  
<span data-ttu-id="5c84e-372">表 5 显示必须在继承自 **IContact** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-372">Table 5 shows the members that must be implemented in the class that inherits from **IContact**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-373">表中未列出的 **IContact** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-373">Any member of the **IContact** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-374">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-374">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
>
> <span data-ttu-id="5c84e-375">有关 **IContact** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContact](https://msdn.microsoft.com/library/UCCollaborationLib.IContact)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-375">For more information about the **IContact** interface and its members, see [UCCollaborationLib.IContact](https://msdn.microsoft.com/library/UCCollaborationLib.IContact).</span></span> 
  
<span data-ttu-id="5c84e-376">**表 5. IContact 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-376">**Table 5. Implementation of the IContact interface**</span></span>

|<span data-ttu-id="5c84e-377">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-377">**Member**</span></span>|<span data-ttu-id="5c84e-378">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-378">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84e-379">**CanStart** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-379">**CanStart** method</span></span>  <br/> |<span data-ttu-id="5c84e-380">如果可以在联系人上启动给定类型的模态，则返回 **true**。</span><span class="sxs-lookup"><span data-stu-id="5c84e-380">Returns **true** if a given type of modality can be started on the contact.</span></span>  <br/> |
|<span data-ttu-id="5c84e-381">**GetContactInformation** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-381">**GetContactInformation** method</span></span>  <br/> |<span data-ttu-id="5c84e-382">从发布联系人获取一个状态项。</span><span class="sxs-lookup"><span data-stu-id="5c84e-382">Gets one presence item from a publishing contact.</span></span>  <br/> |
|<span data-ttu-id="5c84e-383">**BatchGetContactInformation** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-383">**BatchGetContactInformation** method</span></span>  <br/> |<span data-ttu-id="5c84e-384">从发布联系人获取多个状态项。</span><span class="sxs-lookup"><span data-stu-id="5c84e-384">Gets multiple presence items from a publishing contact.</span></span>  <br/> |
|<span data-ttu-id="5c84e-385">**Settings** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-385">**Settings** property</span></span>  <br/> |<span data-ttu-id="5c84e-386">获取联系人属性的集合。</span><span class="sxs-lookup"><span data-stu-id="5c84e-386">Gets a collection of contact properties.</span></span>  <br/> |
|<span data-ttu-id="5c84e-387">**CustomGroups** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-387">**CustomGroups** property</span></span>  <br/> |<span data-ttu-id="5c84e-388">获取联系人所属的组的集合。</span><span class="sxs-lookup"><span data-stu-id="5c84e-388">Gets a collection of groups that the contact is a member of.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-389">在初始化过程中，Office 应用程序通过调用 **IContact.CanStart** 方法来确定本地用户具有的 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="5c84e-389">During the initialization process, the Office application calls the **IContact.CanStart** method to determine the IM capabilities for the local user.</span></span> <span data-ttu-id="5c84e-390">**CanStart** 方法从 [UCCollaborationLib.ModalityTypes](https://msdn.microsoft.com/library/UCCollaborationLib.ModalityTypes) 枚举中获取一个标记作为 __modalityTypes_ 参数的自变量。</span><span class="sxs-lookup"><span data-stu-id="5c84e-390">The **CanStart** method takes a flag from the [UCCollaborationLib.ModalityTypes](https://msdn.microsoft.com/library/UCCollaborationLib.ModalityTypes) enumeration as an argument for the  __modalityTypes_ parameter.</span></span> <span data-ttu-id="5c84e-391">如果当前用户可以参与所请求的模态（即用户能够进行即时消息传递、音频和视频消息传递或应用程序共享），则 **CanStart** 方法将返回 **true**。</span><span class="sxs-lookup"><span data-stu-id="5c84e-391">If the current user can engage in the requested modality (that is, the user is capable of instant messaging, audio and video messaging, or application sharing), the **CanStart** method returns **true**.</span></span>
  
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

<span data-ttu-id="5c84e-392">**GetContactInformation** 方法从 **IContact** 对象检索有关联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-392">The **GetContactInformation** method retrieves information about the contact from the **IContact** object.</span></span> <span data-ttu-id="5c84e-393">调用代码需要从 __contactInformationType_ 参数的 [UCCollaborationLib.ContactInformationType](https://msdn.microsoft.com/library/UCCollaborationLib.ContactInformationType) 枚举中传入一个值，该参数指示要检索的数据。</span><span class="sxs-lookup"><span data-stu-id="5c84e-393">The calling code needs to pass in a value from the [UCCollaborationLib.ContactInformationType](https://msdn.microsoft.com/library/UCCollaborationLib.ContactInformationType) enumeration for the  __contactInformationType_ parameter, which indicates the data to be retrieved.</span></span> 
  
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

<span data-ttu-id="5c84e-394">与 **GetContactInformation** 类似，**BatchGetContactInformation** 方法从 **IContact** 对象检索有关联系人的多个状态项。</span><span class="sxs-lookup"><span data-stu-id="5c84e-394">Similar to the **GetContactInformation**, the **BatchGetContactInformation** method retrieves multiple presence items about the contact from the **IContact** object.</span></span> <span data-ttu-id="5c84e-395">调用代码需要从 __contactInformationTypes_ 参数的 **ContactInformationType** 枚举中传入一个值数组。</span><span class="sxs-lookup"><span data-stu-id="5c84e-395">The calling code needs to pass in an array of values from the **ContactInformationType** enumeration for the  __contactInformationTypes_ parameter.</span></span> <span data-ttu-id="5c84e-396">该方法返回包含请求数据的 [UCCollaborationLib.IContactInformationDictionary](https://msdn.microsoft.com/library/UCCollaborationLib.IContactInformationDictionary) 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-396">The method returns an [UCCollaborationLib.IContactInformationDictionary](https://msdn.microsoft.com/library/UCCollaborationLib.IContactInformationDictionary) object that contains the requested data.</span></span> 
  
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

<span data-ttu-id="5c84e-397">**IContact.Settings** 属性返回 **IContactSettingDictionary** 对象，其中包含有关联系人的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-397">The **IContact.Settings** property returns an **IContactSettingDictionary** object that contains custom properties about the contact.</span></span> 
  
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

<span data-ttu-id="5c84e-398">**IContact.CustomGroups** 属性返回 **IGroupCollection** 对象，其中包含联系人所属的所有组。</span><span class="sxs-lookup"><span data-stu-id="5c84e-398">The **IContact.CustomGroups** property returns an **IGroupCollection** object that includes all of the groups of which the contact is a member.</span></span> 
  
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

### <a name="iself-interface"></a><span data-ttu-id="5c84e-399">ISelf 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-399">ISelf interface</span></span>
<span data-ttu-id="5c84e-400"><a name="off15_IMIntegration_ImplementRequired_ISelf"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-400"></span></span>

<span data-ttu-id="5c84e-401">在初始化过程中，Office 应用程序通过访问 **ILyncClient.Self** 属性来获取当前用户的数据，该属性必须返回 **ISelf** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-401">During the initialization process, the Office application gets the data for the current user by accessing the **ILyncClient.Self** property, which must return an **ISelf** object.</span></span> <span data-ttu-id="5c84e-402">**ISelf** 接口表示本地登录的 IM 客户端应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="5c84e-402">The **ISelf** interface represents the local, signed-in IM client application user.</span></span> 
  
<span data-ttu-id="5c84e-403">表 6 显示必须在继承自 **ISelf** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-403">Table 6 shows the members that must be implemented in the class that inherits from **ISelf**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-404">表中未列出的 **ISelf** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-404">Any member of the **ISelf** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-405">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-405">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
  
<span data-ttu-id="5c84e-406">**表 6. ISelf 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-406">**Table 6. Implementation of the ISelf interface**</span></span>

|<span data-ttu-id="5c84e-407">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-407">**Member**</span></span>|<span data-ttu-id="5c84e-408">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-408">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84e-409">**Contact** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-409">**Contact** property</span></span>  <br/> |<span data-ttu-id="5c84e-410">获取与本地用户关联的 **IContact** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-410">Gets the **IContact** object associated with the local user.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-411">通过 **ISelf.Contact** 属性（返回 **IContact** 对象）公开本地用户的状态、可用模态、组成员资格和联系人类型属性。</span><span class="sxs-lookup"><span data-stu-id="5c84e-411">Presence, available modalities, group membership, and contact type properties for the local user are exposed through the **ISelf.Contact** property (which returns an **IContact** object).</span></span> <span data-ttu-id="5c84e-412">在初始化过程中，Office 应用程序通过访问 **ISelf.Contact** 属性来获取对本地用户的联系信息的引用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-412">During the initialization process, the Office application accesses the **ISelf.Contact** property to get a reference to the contact information for the local user.</span></span> 
  
<span data-ttu-id="5c84e-413">使用以下代码定义从实现 **Contact** 属性的 **ISelf** 接口继承的类。</span><span class="sxs-lookup"><span data-stu-id="5c84e-413">Use the following code to define a class that inherits from the **ISelf** interface that implements the **Contact** property.</span></span> 
  
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

### <a name="icontactmanager-and-_icontactmanagerevents-interfaces"></a><span data-ttu-id="5c84e-414">IContactManager 和 _IContactManagerEvents 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-414">IContactManager and _IContactManagerEvents interfaces</span></span>
<span data-ttu-id="5c84e-415"><a name="off15_IMIntegration_ImplementRequired_IContactManager"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-415"></span></span>

<span data-ttu-id="5c84e-416">**IContactManager** 对象用于管理本地用户的联系人，包括本地用户自己的联系信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-416">The **IContactManager** object manages the contacts for the local user, including the local user's own contact information.</span></span> <span data-ttu-id="5c84e-417">Office 应用程序使用 **IContactManager** 对象来访问与本地用户的联系人对应的 **IContact** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-417">The Office application uses an **IContactManager** object to access **IContact** objects that correspond to the local user's contacts.</span></span> 
  
<span data-ttu-id="5c84e-418">表 7 显示必须在继承自 **IContactManager** 和 **_IContactManagerEvents** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-418">Table 7 shows the members that must be implemented in the class that inherits from **IContactManager** and **_IContactManagerEvents**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-419">表中未列出的 **IContactManager** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-419">Any member of the **IContactManager** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-420">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E\_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-420">Members that are present but not implemented can throw a **NotImplementedException** or **E\_NOTIMPL** error.</span></span> 
>
> <span data-ttu-id="5c84e-421">有关 **IContactManager** 和 **_IContactManagerEvents** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContactManager](https://msdn.microsoft.com/library/UCCollaborationLib.IContactManager) 和 [UCCollaborationLib._IContactManagerEvents](https://msdn.microsoft.com/library/UCCollaborationLib._IContactManagerEvents)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-421">For more information about the **IContactManager** and **_IContactManagerEvents** interfaces and their members, see [UCCollaborationLib.IContactManager](https://msdn.microsoft.com/library/UCCollaborationLib.IContactManager) and [UCCollaborationLib._IContactManagerEvents](https://msdn.microsoft.com/library/UCCollaborationLib._IContactManagerEvents).</span></span> 
  
<span data-ttu-id="5c84e-422">**表 7. IContactManager 和 _IContactManagerEvents 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-422">**Table 7. Implementation of the IContactManager and _IContactManagerEvents interfaces**</span></span>

|<span data-ttu-id="5c84e-423">**接口**</span><span class="sxs-lookup"><span data-stu-id="5c84e-423">**Interface**</span></span>|<span data-ttu-id="5c84e-424">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-424">**Member**</span></span>|<span data-ttu-id="5c84e-425">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-425">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c84e-426">**IContactManager**</span><span class="sxs-lookup"><span data-stu-id="5c84e-426">**IContactManager**</span></span> <br/> |<span data-ttu-id="5c84e-427">**GetContactByUri** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-427">**GetContactByUri** method</span></span>  <br/> |<span data-ttu-id="5c84e-428">使用联系人 URI 查找或创建新的联系人实例。</span><span class="sxs-lookup"><span data-stu-id="5c84e-428">Finds or creates a new contact instance by using the contact URI.</span></span>  <br/> |
||<span data-ttu-id="5c84e-429">**CreateSubscription** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-429">**CreateSubscription** method</span></span>  <br/> |<span data-ttu-id="5c84e-430">创建可用于批量订阅或查询的 **ISubscription** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-430">Creates an **ISubscription** object that can be used for batching subscriptions or queries.</span></span>  <br/> |
||<span data-ttu-id="5c84e-431">**Lookup** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-431">**Lookup** method</span></span>  <br/> |<span data-ttu-id="5c84e-432">查找联系人或通讯组。</span><span class="sxs-lookup"><span data-stu-id="5c84e-432">Looks up a contact or distribution group.</span></span>  <br/> |
|<span data-ttu-id="5c84e-433">**_IContactManagerEvents**</span><span class="sxs-lookup"><span data-stu-id="5c84e-433">**_IContactManagerEvents**</span></span> <br/> |<span data-ttu-id="5c84e-434">**OnGroupAdded** 事件</span><span class="sxs-lookup"><span data-stu-id="5c84e-434">**OnGroupAdded** event</span></span>  <br/> |<span data-ttu-id="5c84e-435">将组添加到组集合时引发。</span><span class="sxs-lookup"><span data-stu-id="5c84e-435">Raised when a group is added to a group collection.</span></span> <span data-ttu-id="5c84e-436">可以从 **IContactManager.Groups** 属性获取更新的组集合。</span><span class="sxs-lookup"><span data-stu-id="5c84e-436">The updated group collection can be obtained from the **IContactManager.Groups** property.</span></span>  <br/> |
||<span data-ttu-id="5c84e-437">**OnGroupRemoved** 事件</span><span class="sxs-lookup"><span data-stu-id="5c84e-437">**OnGroupRemoved** event</span></span>  <br/> |<span data-ttu-id="5c84e-438">从组集合中删除组时引发。</span><span class="sxs-lookup"><span data-stu-id="5c84e-438">Raised when a group is removed from a group collection.</span></span> <span data-ttu-id="5c84e-439">可以从 **IContactManager.Groups** 属性获取更新的组集合。</span><span class="sxs-lookup"><span data-stu-id="5c84e-439">The updated group collection can be obtained from the **IContactManager.Groups** property.</span></span>  <br/> |
||<span data-ttu-id="5c84e-440">**OnSearchProviderStateChanged** 事件</span><span class="sxs-lookup"><span data-stu-id="5c84e-440">**OnSearchProviderStateChanged** event</span></span>  <br/> |<span data-ttu-id="5c84e-441">在搜索提供程序的状态更改时引发。</span><span class="sxs-lookup"><span data-stu-id="5c84e-441">Raised when a search provider's status changes.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-442">Office 通过使用联系人的 SIP 地址来调用 **IContactManager.GetContactByUri**，以便获取联系人的状态信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-442">Office calls **IContactManager.GetContactByUri** to get a contact's presence information, by using the SIP address of the contact.</span></span> <span data-ttu-id="5c84e-443">在 Active Directory 中为联系人配置 SIP 地址时，Office 会为联系人确定此地址并调用 **GetContactByUri**，以便将联系人的 SIP 地址传递给 __contactUri_ 参数。</span><span class="sxs-lookup"><span data-stu-id="5c84e-443">When a contact is configured for an SIP address in the Active Directory, Office determines this address for a contact and calls **GetContactByUri**, passing the SIP address of the contact in for the  __contactUri_ parameter.</span></span> 
  
<span data-ttu-id="5c84e-444">如果 Office 无法确定联系人的 SIP 地址，它会调用 **IContactManager.Lookup** 方法以使用 IM 服务来查找 SIP。</span><span class="sxs-lookup"><span data-stu-id="5c84e-444">When Office cannot determine the SIP address for the contact, it calls the **IContactManager.Lookup** method to find the SIP by using the IM service.</span></span> <span data-ttu-id="5c84e-445">Office 将在此处传入可以为联系人找到的最佳数据（例如，仅联系人的电子邮件地址）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-445">Here Office passes in the best data that it can find for the contact (for example, just the email address for the contact).</span></span> <span data-ttu-id="5c84e-446">**Lookup** 方法通过异步方式返回 **AsynchronousOperation** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-446">The **Lookup** method asynchronously returns an **AsynchronousOperation** object.</span></span> <span data-ttu-id="5c84e-447">当它调用回调时，除了联系人的 URI 之外，**Lookup** 方法应该还会返回操作的成功或失败信息。</span><span class="sxs-lookup"><span data-stu-id="5c84e-447">When it invokes the callback, the **Lookup** method should return the success or failure of the operation in addition to the URI of the contact.</span></span> 
  
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

<span data-ttu-id="5c84e-448">Office 应用程序需要订阅各个联系人的状态更改。</span><span class="sxs-lookup"><span data-stu-id="5c84e-448">The Office application needs to subscribe to presence changes for an individual contact.</span></span> <span data-ttu-id="5c84e-449">因此，当联系人的当前状态发生更改时，IM 服务器会向 IM 客户端应用程序发出警报，从而向 Office 应用程序发出警报。</span><span class="sxs-lookup"><span data-stu-id="5c84e-449">Thus, when a contact's presence status changes, the IM server alerts the IM client application—thereby alerting the Office application.</span></span> <span data-ttu-id="5c84e-450">为此，Office 应用程序将调用 **IContactManager.CreateSubscription** 方法，以便为此请求创建新的 **IContactSubscription** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-450">To do this, the Office application calls the **IContactManager.CreateSubscription** method to create a new **IContactSubscription** object for this request.</span></span> 
  
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

### <a name="igroup-and-igroupcollection-interfaces"></a><span data-ttu-id="5c84e-451">IGroup 和 IGroupCollection 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-451">IGroup and IGroupCollection interfaces</span></span>
<span data-ttu-id="5c84e-452"><a name="off15_IMIntegration_ImplementRequired_IGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-452"></span></span>

<span data-ttu-id="5c84e-453">**IGroup** 对象表示具有附加属性的联系人集合，用于通过集合组名称标识联系人集合。</span><span class="sxs-lookup"><span data-stu-id="5c84e-453">The **IGroup** object represents a collection of contacts with additional properties for identifying the contact collection by a collective group name.</span></span> <span data-ttu-id="5c84e-454">**IGroupCollection** 对象表示由本地用户和 IM 客户端应用程序定义的 **IGroup** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="5c84e-454">An **IGroupCollection** object represents a collection of **IGroup** objects defined by a local user and the IM client application.</span></span> <span data-ttu-id="5c84e-455">Office 应用程序使用 **IGroupCollection** 和 **IGroup** 对象来访问本地用户的联系人。</span><span class="sxs-lookup"><span data-stu-id="5c84e-455">The Office application uses the **IGroupCollection** and **IGroup** objects to access the local user's contacts.</span></span> 
  
<span data-ttu-id="5c84e-456">表 9 显示必须在继承自下表中的 **IGroup** 和 **IGroupCollection** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-456">Table 9 shows the members that must be implemented in the classes that inherit from **IGroup** and **IGroupCollection** in the following table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5c84e-457">表中未列出的 **IGroup** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-457">Any member of the **IGroup** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-458">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-458">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span> 
>
> <span data-ttu-id="5c84e-459">有关 **IGroup** 和 **IGroupCollection** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IGroup](https://msdn.microsoft.com/library/UCCollaborationLib.IGroup) 和 [UCCollaborationLib.IGroupCollection](https://msdn.microsoft.com/library/UCCollaborationLib.IGroupCollection)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-459">For more information about the **IGroup** and **IGroupCollection** interfaces and their members, see [UCCollaborationLib.IGroup](https://msdn.microsoft.com/library/UCCollaborationLib.IGroup) and [UCCollaborationLib.IGroupCollection](https://msdn.microsoft.com/library/UCCollaborationLib.IGroupCollection).</span></span> 
  
<span data-ttu-id="5c84e-460">**表 9. IGroup 和 IGroupCollection 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-460">**Table 9. Implementation of the IGroup and IGroupCollection interfaces**</span></span>

|<span data-ttu-id="5c84e-461">**接口**</span><span class="sxs-lookup"><span data-stu-id="5c84e-461">**Interface**</span></span>|<span data-ttu-id="5c84e-462">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-462">**Member**</span></span>|<span data-ttu-id="5c84e-463">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-463">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c84e-464">**IGroupCollection**</span><span class="sxs-lookup"><span data-stu-id="5c84e-464">**IGroupCollection**</span></span> <br/> |<span data-ttu-id="5c84e-465">**Count** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-465">**Count** property</span></span>  <br/> |<span data-ttu-id="5c84e-466">返回集合中的 **IGroup** 对象的计数</span><span class="sxs-lookup"><span data-stu-id="5c84e-466">Returns the count of **IGroup** objects in the collection</span></span>  <br/> |
||<span data-ttu-id="5c84e-467">**Item** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-467">**Item** property</span></span>  <br/> |<span data-ttu-id="5c84e-468">返回集合中指定索引处的 **IGroup** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-468">Returns the **IGroup** object at the specified index in the collection.</span></span>  <br/> |
|<span data-ttu-id="5c84e-469">**IGroup**</span><span class="sxs-lookup"><span data-stu-id="5c84e-469">**IGroup**</span></span> <br/> |<span data-ttu-id="5c84e-470">**Id** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-470">**Id** property</span></span>  <br/> |<span data-ttu-id="5c84e-471">返回组 ID。</span><span class="sxs-lookup"><span data-stu-id="5c84e-471">Returns the ID of the group.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-472">当 Office 应用程序获取本地用户的信息时，它通过调用 **IContact.CustomGroups** 属性来访问联系人（本地用户）的组成员身份，该属性返回 **IGroupCollection** 对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-472">When the Office application gets the information for the local user, it accesses the group memberships of the contact (local user) by calling the **IContact.CustomGroups** property, which returns an **IGroupCollection** object.</span></span> <span data-ttu-id="5c84e-473">**IGroupCollection** 必须包含 **IGroup** 对象的数组（或 **List**）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-473">The **IGroupCollection** must contain an array (or **List**) of **IGroup** objects.</span></span> <span data-ttu-id="5c84e-474">派生自 **IGroupCollection** 的类必须公开 **Count** 属性（它返回集合中的项目数）和索引器方法 **this(int)**（它返回集合中的 **IGroup** 对象）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-474">The class that derives from **IGroupCollection** must expose a **Count** property, which returns the number of items in the collection, and an indexer method, **this(int)**, which returns an **IGroup** object from the collection.</span></span> 
  
### <a name="icontactsubscription-interface"></a><span data-ttu-id="5c84e-475">IContactSubscription 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-475">IContactSubscription interface</span></span>
<span data-ttu-id="5c84e-476"><a name="off15_IMIntegration_ImplementRequired_IContactSubscription"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-476"></span></span>

<span data-ttu-id="5c84e-477">**IContactSubscription** 接口允许你指定接收状态信息更新的联系人以及触发通知的状态信息类型。</span><span class="sxs-lookup"><span data-stu-id="5c84e-477">The **IContactSubscription** interface allows you to specify the contacts to receive presence information updates for and the types of presence information that trigger a notification.</span></span> <span data-ttu-id="5c84e-478">Office 应用程序使用 **IContactSubscription** 对象来注册对联系人状态的更改。</span><span class="sxs-lookup"><span data-stu-id="5c84e-478">Office applications use an **IContactSubscription** object to register changes to contact's presence status.</span></span> 
  
<span data-ttu-id="5c84e-479">表 10 显示必须在继承自 **IContactSubscription** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-479">Table 10 shows the members that must be implemented in the classes that inherit from **IContactSubscription**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-480">表中未列出的 **IContactSubscription** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-480">Any member of the **IContactSubscription** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-481">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-481">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span>
>
> <span data-ttu-id="5c84e-482">有关 **IContactSubscription** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContactSubscription](https://msdn.microsoft.com/library/UCCollaborationLib.IContactSubscription)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-482">For more information about the **IContactSubscription** interface and its members, see [UCCollaborationLib.IContactSubscription](https://msdn.microsoft.com/library/UCCollaborationLib.IContactSubscription).</span></span> 
  
<span data-ttu-id="5c84e-483">**表 10. IContactSubscription 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-483">**Table 10. Implementation of the IContactSubscription interface**</span></span>

|<span data-ttu-id="5c84e-484">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-484">**Member**</span></span>|<span data-ttu-id="5c84e-485">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-485">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84e-486">**AddContact** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-486">**AddContact** method</span></span>  <br/> |<span data-ttu-id="5c84e-487">将联系人添加到订阅对象。</span><span class="sxs-lookup"><span data-stu-id="5c84e-487">Adds a contact to the subscription object.</span></span>  <br/> |
|<span data-ttu-id="5c84e-488">**Subscribe** 方法</span><span class="sxs-lookup"><span data-stu-id="5c84e-488">**Subscribe** method</span></span>  <br/> |<span data-ttu-id="5c84e-489">帮助 IM 客户端应用程序监视联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-489">Helps the IM client application to monitor presence for a contact.</span></span>  <br/> |
   
<span data-ttu-id="5c84e-490">**IContactSubscription** 接口必须包含对其监视的所有 **IContact** 对象的引用（使用数组或 **List**）。</span><span class="sxs-lookup"><span data-stu-id="5c84e-490">The **IContactSubscription** interface must contain a reference to all the **IContact** objects that it monitors, using an array or a **List**.</span></span> <span data-ttu-id="5c84e-491">**IContactSubscription.AddContact** 方法为 **IContactSubscription** 对象的基础数据结构添加 **IContact**对象，以便添加要监视状态更改的新联系人。</span><span class="sxs-lookup"><span data-stu-id="5c84e-491">The **IContactSubscription.AddContact** method adds an **IContact** object for the to the underlying data structure of the **IContactSubscription** object, thereby adding a new contact to monitor for presence changes.</span></span> 
  
```cs
// Store references to all of the IContact objects to subscribe to.
private List<IMClientContact> _subscribedContacts;
// Add a new IContact object to the collection of contacts.
public void AddContact(IMClientContact _contact)
{
    this._subscribedContacts.Add(_contact);
}
```

<span data-ttu-id="5c84e-492">**IContactSubscription.Subscribe** 方法允许 IM 客户端应用程序访问联系人的状态观察者。</span><span class="sxs-lookup"><span data-stu-id="5c84e-492">The **IContactSubscription.Subscribe** method allows an IM client application to access presence observers for the contact.</span></span> <span data-ttu-id="5c84e-493">它可以使用轮询策略从服务器获取 IM 客户端应用程序订阅的联系人的状态。</span><span class="sxs-lookup"><span data-stu-id="5c84e-493">It can use a polling strategy to get the presence from the server for the contacts for that the IM client application has subscribed to.</span></span> <span data-ttu-id="5c84e-494">如果要请求用户联系人列表之外的联系人（例如，来自更大公共网络的联系人）的状态，则 **Subscribe** 方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="5c84e-494">The **Subscribe** method is helpful in situations where presence is requested for someone outside of a user's contact list (for example, from a larger public network).</span></span> 
  
### <a name="icontactendpoint-interface"></a><span data-ttu-id="5c84e-495">IContactEndPoint 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-495">IContactEndPoint interface</span></span>
<span data-ttu-id="5c84e-496"><a name="off15_IMIntegration_ImplementRequired_IContactEndPoint"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-496"></span></span>

<span data-ttu-id="5c84e-497">**IContactEndPoint** 表示联系人电话号码集中的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5c84e-497">The **IContactEndPoint** represents a telephone number from a contact's collection of telephone numbers.</span></span> 
  
<span data-ttu-id="5c84e-498">表 11 显示必须在继承自 **IContactEndPoint** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-498">Table 11 shows the members that must be implemented in the classes that inherit from **IContactEndPoint**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-499">表中未列出的 **IContactEndPoint** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-499">Any member of the **IContactEndPoint** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-500">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-500">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span>
>
> <span data-ttu-id="5c84e-501">有关 **IContactEndPoint** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.IContactEndpoint](https://msdn.microsoft.com/library/UCCollaborationLib.IContactEndpoint)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-501">For more information about the **IContactEndPoint** interface and its members, see [UCCollaborationLib.IContactEndpoint](https://msdn.microsoft.com/library/UCCollaborationLib.IContactEndpoint).</span></span> 
  
<span data-ttu-id="5c84e-502">**表 11. IContactEndPoint 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-502">**Table 11. Implementation of the IContactEndPoint interface**</span></span>

|<span data-ttu-id="5c84e-503">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-503">**Member**</span></span>|<span data-ttu-id="5c84e-504">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-504">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84e-505">**DisplayName** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-505">**DisplayName** property</span></span>  <br/> |<span data-ttu-id="5c84e-506">获取显示字符串。</span><span class="sxs-lookup"><span data-stu-id="5c84e-506">Gets the display string.</span></span>  <br/> |
|<span data-ttu-id="5c84e-507">**Type** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-507">**Type** property</span></span>  <br/> |<span data-ttu-id="5c84e-508">获取联系人端点类型</span><span class="sxs-lookup"><span data-stu-id="5c84e-508">Gets the contact endpoint type</span></span>  <br/> |
|<span data-ttu-id="5c84e-509">**Uri** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-509">**Uri** property</span></span>  <br/> |<span data-ttu-id="5c84e-510">获取联系人 URI。</span><span class="sxs-lookup"><span data-stu-id="5c84e-510">Gets the contact URI.</span></span>  <br/> |
   
### <a name="ilocalestring-interface"></a><span data-ttu-id="5c84e-511">ILocaleString 接口</span><span class="sxs-lookup"><span data-stu-id="5c84e-511">ILocaleString interface</span></span>
<span data-ttu-id="5c84e-512"><a name="off15_IMIntegration_ImplementRequired_ILocaleString"> </a></span><span class="sxs-lookup"><span data-stu-id="5c84e-512"></span></span>

<span data-ttu-id="5c84e-513">**ILocaleString** 是本地化的字符串结构，包含本地化字符串和本地化的区域设置 ID。</span><span class="sxs-lookup"><span data-stu-id="5c84e-513">The **ILocaleString** is a localized string structure that contains both a localized string and the locale ID of the localization.</span></span> <span data-ttu-id="5c84e-514">**ILocaleString** 接口用于格式化联系人卡片上的自定义状态字符串。</span><span class="sxs-lookup"><span data-stu-id="5c84e-514">The **ILocaleString** interface is used to format the custom status string on the contact card.</span></span> 
  
<span data-ttu-id="5c84e-515">表 12 显示必须在继承自 **ILocaleString** 的类中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="5c84e-515">Table 12 shows the members that must be implemented in the classes that inherit from **ILocaleString**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c84e-516">表中未列出的 **ILocaleString** 接口的任何成员都必须存在，但不需要实现。</span><span class="sxs-lookup"><span data-stu-id="5c84e-516">Any member of the **ILocaleString** interface not listed in the table must be present but does not need to be implemented.</span></span> <span data-ttu-id="5c84e-517">存在但未实现的成员可能会引发 **NotImplementedException** 或 **E_NOTIMPL** 错误。</span><span class="sxs-lookup"><span data-stu-id="5c84e-517">Members that are present but not implemented can throw a **NotImplementedException** or **E_NOTIMPL** error.</span></span>
>
> <span data-ttu-id="5c84e-518">有关 **ILocalString** 接口及其成员的详细信息，请参阅 [UCCollaborationLib.ILocaleString](https://msdn.microsoft.com/library/UCCollaborationLib.ILocaleString)。</span><span class="sxs-lookup"><span data-stu-id="5c84e-518">For more information about the **ILocalString** interface and its members, see [UCCollaborationLib.ILocaleString](https://msdn.microsoft.com/library/UCCollaborationLib.ILocaleString).</span></span> 
  
<span data-ttu-id="5c84e-519">**表 12. ILocaleString 接口的实现**</span><span class="sxs-lookup"><span data-stu-id="5c84e-519">**Table 12. Implementation of the ILocaleString interface**</span></span>

|<span data-ttu-id="5c84e-520">**成员**</span><span class="sxs-lookup"><span data-stu-id="5c84e-520">**Member**</span></span>|<span data-ttu-id="5c84e-521">**说明**</span><span class="sxs-lookup"><span data-stu-id="5c84e-521">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84e-522">**LocaleId** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-522">**LocaleId** property</span></span>  <br/> |<span data-ttu-id="5c84e-523">获取区域设置 ID。</span><span class="sxs-lookup"><span data-stu-id="5c84e-523">Gets the locale ID.</span></span>  <br/> |
|<span data-ttu-id="5c84e-524">**Value** 属性</span><span class="sxs-lookup"><span data-stu-id="5c84e-524">**Value** property</span></span>  <br/> |<span data-ttu-id="5c84e-525">获取字符串。</span><span class="sxs-lookup"><span data-stu-id="5c84e-525">Gets the string.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5c84e-526">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c84e-526">See also</span></span>

- <span data-ttu-id="5c84e-527">[UCCollaborationLib](https://msdn.microsoft.com/library/UCCollaborationLib) 命名空间</span><span class="sxs-lookup"><span data-stu-id="5c84e-527">[UCCollaborationLib](https://msdn.microsoft.com/library/UCCollaborationLib) namespace</span></span> 
    

