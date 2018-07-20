---
title: 从 iOS 应用程序与 Office 集成
manager: soliver
ms.date: 06/04/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: f3a277ba-7ba1-4eea-83b5-915b409f3093
description: Office for iOS 提供了一个可扩展的解决方案，以便能够与第三方应用程序集成。本文介绍如何从 iOS 应用程序与 Office 集成，如何通过将用户从您的应用程序传递到 Office 然后再将他们返回到您的应用程序来实现集成。
ms.openlocfilehash: 2ba8e1a157953705b60ff0cac7d62bafade0c469
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774105"
---
# <a name="integrate-with-office-from-ios-applications"></a><span data-ttu-id="4c2cb-104">从 iOS 应用程序与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="4c2cb-104">Integrate with Office from iOS applications</span></span>

<span data-ttu-id="4c2cb-p102">Office for iOS 提供了一个可扩展的解决方案，以便能够与第三方应用程序集成。本文介绍如何从 iOS 应用程序与 Office 集成，如何通过将用户从您的应用程序传递到 Office 然后再将他们返回到您的应用程序来实现集成。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p102">Office for iOS provides an extensible solution that enables integration with third-party applications. This article describes how you can integrate with Office from your iOS application by passing users from your application to Office, and then returning them to your application.</span></span>
  
<span data-ttu-id="4c2cb-p103">可以使在 iOS 设备上运行 Office 的用户能够从任何应用程序打开和编辑存储在 SharePoint 或 OneDrive 中的文件，然后在完成编辑文件后快速将其返回到原始应用程序中。若要执行此操作，您可以通过协议处理程序将文件传递到 Office，并确保采用 Office 可以理解的方式来调用 Office。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p103">You can enable users who are running Office on an iOS device to open and edit files stored in SharePoint or OneDrive from any application, and then quickly return them to the original application when they're done editing the file. To do this, you pass files to Office via protocol handlers, and you make sure that Office is invoked in a way that Office can understand.</span></span>
  
<span data-ttu-id="4c2cb-109">当用户完成了对某个文件的编辑后，假如在 Office 应用程序启动时您将特定信息传递给 了它，则用户可以选择 Office 应用程序中的后退箭头关闭该文档，并返回到原始存储应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-109">When a user is done editing a file, they can choose the back arrow in the Office application to close the document and return to the original storage application, provided you pass specific information to the Office application when it launches.</span></span>
  
## <a name="verify-that-office-has-been-installed"></a><span data-ttu-id="4c2cb-110">验证是否已安装 Office</span><span class="sxs-lookup"><span data-stu-id="4c2cb-110">Verify that Office has been installed</span></span>

<span data-ttu-id="4c2cb-p104">引用的应用程序将首先需要验证特定 Office 应用程序是否已安装。以下 Office 应用程序可以安装在 iOS 设备上用于查看和编辑文档：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p104">Your referring application will first need to verify that a particular Office application is installed. The following Office applications can be installed on iOS devices for document viewing and editing:</span></span>
  
- <span data-ttu-id="4c2cb-113">Excel</span><span class="sxs-lookup"><span data-stu-id="4c2cb-113">Excel</span></span>
    
- <span data-ttu-id="4c2cb-114">OneNote</span><span class="sxs-lookup"><span data-stu-id="4c2cb-114">OneNote</span></span>
    
- <span data-ttu-id="4c2cb-115">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4c2cb-115">PowerPoint</span></span>
    
- <span data-ttu-id="4c2cb-116">Word</span><span class="sxs-lookup"><span data-stu-id="4c2cb-116">Word</span></span>
    
<span data-ttu-id="4c2cb-p105">使用 [canOpenURL](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html) 方法确定您的应用程序是否可以打开资源。此方法将资源的 URL 作为参数，如果接受 URL 的应用程序不可用，则返回 **No**。如果 **canOpenURL** 返回 **No**，则您将需要提示用户安装 Office。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p105">Use the [canOpenURL](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html) method to determine whether your application can open the resource. This method takes the URL for the resource as a parameter, and returns **No** if the application that accepts the URL is not available. If **canOpenURL** returns **No**, you'll need to prompt the user to install Office.</span></span>
  
### <a name="prompt-the-user-to-install-office"></a><span data-ttu-id="4c2cb-120">提示用户安装 Office</span><span class="sxs-lookup"><span data-stu-id="4c2cb-120">Prompt the user to install Office</span></span>

 <span data-ttu-id="4c2cb-p106">如果未安装某个特定 Office 应用程序，您可以使用 [SKProductViewController](https://developer.apple.com/library/ios/documentation/StoreKit/Reference/SKITunesProductViewController_Ref/index.html) 对象，以在您的应用程序中呈现 iTunes 应用商店并向用户显示要安装的 Office 应用程序。下表列出了要用于在商店工具包产品视图控制器中调用每个 Office 应用程序的 iTunes 标识符。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p106">If a particular Office application is not installed, you can use an [SKProductViewController](https://developer.apple.com/library/ios/documentation/StoreKit/Reference/SKITunesProductViewController_Ref/index.html) object to render the iTunes app store in your application and show the user the Office application to install. The following table lists the iTunes identifier to use to invoke each Office application in the Store Kit Product View Controller.</span></span> 
  
|<span data-ttu-id="4c2cb-123">**Office 应用程序**</span><span class="sxs-lookup"><span data-stu-id="4c2cb-123">**Office application**</span></span>|<span data-ttu-id="4c2cb-124">**iTunes 标识符**</span><span class="sxs-lookup"><span data-stu-id="4c2cb-124">**iTunes identifier**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c2cb-125">Excel</span><span class="sxs-lookup"><span data-stu-id="4c2cb-125">Excel</span></span>  <br/> |[<span data-ttu-id="4c2cb-126">https://itunes.apple.com/us/app/microsoft-excel/id586683407?mt=8&amp;uo=4</span><span class="sxs-lookup"><span data-stu-id="4c2cb-126">https://itunes.apple.com/us/app/microsoft-excel/id586683407?mt=8&amp;uo=4</span></span>](https://itunes.apple.com/us/app/microsoft-excel/id586683407?mt=8&amp;uo=4) <br/> |
|<span data-ttu-id="4c2cb-127">OneNote (iPad)</span><span class="sxs-lookup"><span data-stu-id="4c2cb-127">OneNote (iPad)</span></span>  <br/> |[<span data-ttu-id="4c2cb-128">https://itunes.apple.com/us/app/microsoft-onenote-for-ipad/id478105721?mt=8&amp;uo=4</span><span class="sxs-lookup"><span data-stu-id="4c2cb-128">https://itunes.apple.com/us/app/microsoft-onenote-for-ipad/id478105721?mt=8&amp;uo=4</span></span>](https://itunes.apple.com/us/app/microsoft-onenote-for-ipad/id478105721?mt=8&amp;uo=4) <br/> |
|<span data-ttu-id="4c2cb-129">OneNote (iPhone)</span><span class="sxs-lookup"><span data-stu-id="4c2cb-129">OneNote (iPhone)</span></span>  <br/> |[<span data-ttu-id="4c2cb-130">https://itunes.apple.com/us/app/microsoft-onenote-for-iphone/id410395246?mt=8&amp;uo=4</span><span class="sxs-lookup"><span data-stu-id="4c2cb-130">https://itunes.apple.com/us/app/microsoft-onenote-for-iphone/id410395246?mt=8&amp;uo=4</span></span>](https://itunes.apple.com/us/app/microsoft-onenote-for-iphone/id410395246?mt=8&amp;uo=4) <br/> |
|<span data-ttu-id="4c2cb-131">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4c2cb-131">PowerPoint</span></span>  <br/> |[<span data-ttu-id="4c2cb-132">https://itunes.apple.com/us/app/microsoft-powerpoint/id586449534?mt=8&amp;uo=4</span><span class="sxs-lookup"><span data-stu-id="4c2cb-132">https://itunes.apple.com/us/app/microsoft-powerpoint/id586449534?mt=8&amp;uo=4</span></span>](https://itunes.apple.com/us/app/microsoft-powerpoint/id586449534?mt=8&amp;uo=4) <br/> |
|<span data-ttu-id="4c2cb-133">Word</span><span class="sxs-lookup"><span data-stu-id="4c2cb-133">Word</span></span>  <br/> |[<span data-ttu-id="4c2cb-134">https://itunes.apple.com/us/app/microsoft-word/id586447913?mt=8&amp;uo=4</span><span class="sxs-lookup"><span data-stu-id="4c2cb-134">https://itunes.apple.com/us/app/microsoft-word/id586447913?mt=8&amp;uo=4</span></span>](https://itunes.apple.com/us/app/microsoft-word/id586447913?mt=8&amp;uo=4) <br/> |
   
## <a name="invoke-office"></a><span data-ttu-id="4c2cb-135">调用 Office</span><span class="sxs-lookup"><span data-stu-id="4c2cb-135">Invoke Office</span></span>

<span data-ttu-id="4c2cb-136">当安装 Office 应用程序时，引用应用程序可以通过传递以下详细信息调用 Office：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-136">When the Office application is installed, your referring application can invoke Office by passing the following details:</span></span> 
  
- <span data-ttu-id="4c2cb-137">Office 协议</span><span class="sxs-lookup"><span data-stu-id="4c2cb-137">Office protocol</span></span>
    
- <span data-ttu-id="4c2cb-138">打开模式</span><span class="sxs-lookup"><span data-stu-id="4c2cb-138">Open mode</span></span>
    
- <span data-ttu-id="4c2cb-139">URL</span><span class="sxs-lookup"><span data-stu-id="4c2cb-139">URL</span></span>
    
- <span data-ttu-id="4c2cb-140">Passback 协议</span><span class="sxs-lookup"><span data-stu-id="4c2cb-140">Passback protocol</span></span>
    
- <span data-ttu-id="4c2cb-141">文档上下文</span><span class="sxs-lookup"><span data-stu-id="4c2cb-141">Document context</span></span>
    
<span data-ttu-id="4c2cb-142">架构格式：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-142">Schema format:</span></span>
  
 `<Office protocol><open mode>|u|<URL>|p|<passback protocol>|c|<document context>`
  
<span data-ttu-id="4c2cb-143">以下示例显示调用 Word 文件以供编辑的请求：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-143">The following example shows a request to invoke a Word file for editing:</span></span>
  
 `ms-word:ofe|u|https://contoso/Q4/budget.docx|p|clouddrive|c|folderviewQ4`
  
### <a name="office-protocols"></a><span data-ttu-id="4c2cb-144">Office 协议</span><span class="sxs-lookup"><span data-stu-id="4c2cb-144">Office protocols</span></span>

<span data-ttu-id="4c2cb-145">下表列出了每个 Office 应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-145">The following table lists the protocols for each Office application.</span></span> 
  
|<span data-ttu-id="4c2cb-146">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="4c2cb-146">**Application**</span></span>|<span data-ttu-id="4c2cb-147">**协议**</span><span class="sxs-lookup"><span data-stu-id="4c2cb-147">**Protocol**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c2cb-148">Excel</span><span class="sxs-lookup"><span data-stu-id="4c2cb-148">Excel</span></span>  <br/> |<span data-ttu-id="4c2cb-149">ms-excel:</span><span class="sxs-lookup"><span data-stu-id="4c2cb-149">ms-excel:</span></span>  <br/> |
|<span data-ttu-id="4c2cb-150">OneNote</span><span class="sxs-lookup"><span data-stu-id="4c2cb-150">OneNote</span></span>  <br/> |<span data-ttu-id="4c2cb-151">onenote:</span><span class="sxs-lookup"><span data-stu-id="4c2cb-151">onenote:</span></span>  <br/> |
|<span data-ttu-id="4c2cb-152">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4c2cb-152">PowerPoint</span></span>  <br/> |<span data-ttu-id="4c2cb-153">ms-powerpoint:</span><span class="sxs-lookup"><span data-stu-id="4c2cb-153">ms-powerpoint:</span></span>  <br/> |
|<span data-ttu-id="4c2cb-154">Word</span><span class="sxs-lookup"><span data-stu-id="4c2cb-154">Word</span></span>  <br/> |<span data-ttu-id="4c2cb-155">ms-word:</span><span class="sxs-lookup"><span data-stu-id="4c2cb-155">ms-word:</span></span>  <br/> |
   
### <a name="open-mode"></a><span data-ttu-id="4c2cb-156">打开模式</span><span class="sxs-lookup"><span data-stu-id="4c2cb-156">Open mode</span></span>

<span data-ttu-id="4c2cb-p107">Office 应用程序可以直接在视图 (ofv) 或编辑 (ofe) 模式下打开文件。编辑模式为默认设置。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p107">Office applications can open files directly into view (ofv) or edit (ofe) mode. Edit mode is the default.</span></span> 
  
<span data-ttu-id="4c2cb-159">架构格式：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-159">Schema format:</span></span>
  
 `<ofv or ofe>`
  
### <a name="url"></a><span data-ttu-id="4c2cb-160">URL</span><span class="sxs-lookup"><span data-stu-id="4c2cb-160">URL</span></span>

<span data-ttu-id="4c2cb-161">URL 包括三个部分：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-161">The URL includes three parts:</span></span> 
  
- <span data-ttu-id="4c2cb-162">文件将在编辑 (ofe) 模式下打开的声明</span><span class="sxs-lookup"><span data-stu-id="4c2cb-162">The declaration that the file will be opened for edit (ofe)</span></span>
    
- <span data-ttu-id="4c2cb-163">URL 描述符 (|u|)</span><span class="sxs-lookup"><span data-stu-id="4c2cb-163">The URL descriptor (|u|)</span></span>
    
- <span data-ttu-id="4c2cb-164">URL</span><span class="sxs-lookup"><span data-stu-id="4c2cb-164">The URL</span></span>
    
<span data-ttu-id="4c2cb-p108">URL 必须进行编码，并且必须是指向文件（不是重定向）的直接链接。如果 URL 的格式不是 Office 能够处理的格式，或者只是下载失败，Office 就不会将用户返回到调用应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p108">The URL has to be encoded and must be a direct link to the file (not a redirect). If the URL is in a format that Office cannot handle, or the download simply fails, Office will not return the user to the invoking application.</span></span> 
  
<span data-ttu-id="4c2cb-167">架构格式：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-167">Schema format:</span></span>
  
 `|u|<document URL>`
  
### <a name="passback-protocol-optional"></a><span data-ttu-id="4c2cb-168">Passback 协议（可选）</span><span class="sxs-lookup"><span data-stu-id="4c2cb-168">Passback protocol (optional)</span></span>

<span data-ttu-id="4c2cb-p109">如果您希望在用户选择后退箭头时，Office 将用户返回到您的 iOS 应用程序，那么调用应用程序将需要使用 passback 协议，包括后接应用程序协议（不带冒号）的描述符"|p|"。您将需要确保您的应用程序可以正确地处理来自 Office 的响应。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p109">If you want Office to return users to your iOS application when they choose the back arrow, the invoking application will need to use the passback protocol, which includes the descriptor '|p|' followed by the app protocol (without a colon). You'll need to ensure that your application can properly handle the response from Office.</span></span>
  
<span data-ttu-id="4c2cb-171">架构格式：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-171">Schema format:</span></span>
  
 `|p|<passback protocol>`
  
### <a name="document-context-optional"></a><span data-ttu-id="4c2cb-172">文档上下文（可选）</span><span class="sxs-lookup"><span data-stu-id="4c2cb-172">Document context (optional)</span></span>

<span data-ttu-id="4c2cb-p110">Office 不使用文档上下文，但引用应用程序可能在 Office 传递回用户时需要用到它。如果您希望文档上下文返回到您的应用程序，则使用描述符 "|c|"，后接您希望将其作为字符串的上下文。除了由操作系统施加的限制以外，Office 不会限制该字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p110">Office doesn't use the document context, but the referring application might need it when Office passes a user back. If you want the document context to be returned to your application, use the descriptor '|c|' followed by the context that you want as a string. Office does not limit the length of the string, beyond any limits imposed by the operating system.</span></span>
  
<span data-ttu-id="4c2cb-176">架构格式：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-176">Schema format:</span></span>
  
 `|c|<document context>`
  
## <a name="return-users-to-the-referring-application"></a><span data-ttu-id="4c2cb-177">将用户返回到引用应用程序</span><span class="sxs-lookup"><span data-stu-id="4c2cb-177">Return users to the referring application</span></span>

<span data-ttu-id="4c2cb-p111">出于安全考虑，如果文件已成功打开，则 Office 仅将用户返回到引用应用程序。 当用户选择后退箭头，Office 将根据 passback 协议、打开模式、URL、上载待定状态和文档上下文来响应调用应用程序。上载待定状态使用描述符 "|z|"，其值为 "Yes" 或 "No"。</span><span class="sxs-lookup"><span data-stu-id="4c2cb-p111">For security reasons, Office only returns users to the referring application if the file opened successfully. When the user chooses the back arrow, Office responds to the invoking application with the passback protocol, open mode, URL, upload pending status, and document context. The upload pending status uses the descriptor |z|, and is either yes or no.</span></span>
  
<span data-ttu-id="4c2cb-181">架构格式：</span><span class="sxs-lookup"><span data-stu-id="4c2cb-181">Schema format:</span></span>
  
 `<app protocol>:ofe|u|<URL>|z|<yes or no>|c|<doc context> Example: clouddrive:ofe|u|https://contoso/Q4/budget.docx|z|no|c|folderviewQ4`
  
## <a name="see-also"></a><span data-ttu-id="4c2cb-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c2cb-182">See also</span></span>
<span data-ttu-id="4c2cb-183"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="4c2cb-183"></span></span>

- [<span data-ttu-id="4c2cb-184">canOpenURL 方法</span><span class="sxs-lookup"><span data-stu-id="4c2cb-184">canOpenURL method</span></span>](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html)
    
- [<span data-ttu-id="4c2cb-185">UIApplication 类</span><span class="sxs-lookup"><span data-stu-id="4c2cb-185">UIApplication class</span></span>](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html)
    
- [<span data-ttu-id="4c2cb-186">SKProductViewController 对象</span><span class="sxs-lookup"><span data-stu-id="4c2cb-186">SKProductViewController object</span></span>](https://developer.apple.com/library/ios/documentation/StoreKit/Reference/SKITunesProductViewController_Ref/index.html)
    
