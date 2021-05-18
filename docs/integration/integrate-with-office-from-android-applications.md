---
title: 从 Android 应用程序与 Office 集成
manager: soliver
ms.date: 06/18/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: a765fa49-a272-4047-9147-59cc68e5dd27
description: Office for Android 提供了一个可扩展的的解决方案，可与第三方应用程序集成。您可以将用户从您的应用程序传递到 Office，从 Android 应用程序与 Office 集成。
ms.openlocfilehash: 4e674b3d66f3acba7e9c9c19e716ff0d73d803b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303148"
---
# <a name="integrate-with-office-from-android-applications"></a><span data-ttu-id="633ab-104">从 Android 应用程序与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="633ab-104">Integrate with Office from Android applications</span></span>

<span data-ttu-id="633ab-p102">Office for Android 提供了一个可扩展的的解决方案，可与第三方应用程序集成。您可以将用户从您的应用程序传递到 Office，从 Android 应用程序与 Office 集成。</span><span class="sxs-lookup"><span data-stu-id="633ab-p102">Office for Android provides an extensible solution that enables integration with third-party applications. You can integrate with Office from your Android application by passing users from your application to Office.</span></span>
  
<span data-ttu-id="633ab-p103">您可以让在 Android 设备上运行 Office 的用户从任何应用程序打开和编辑存储在 SharePoint 或 OneDrive 中的文件。为此，您可以通过协议处理程序将文件传递到 Office，并确保以 Office 可以理解的方式来调用 Office。</span><span class="sxs-lookup"><span data-stu-id="633ab-p103">You can enable users who are running Office on an Android device to open and edit files stored in SharePoint or OneDrive from any application. To do this, you pass files to Office via protocol handlers, and you make sure that Office is invoked in a way that Office can understand.</span></span>
  
<span data-ttu-id="633ab-109">用户完成编辑文件后，可以选择设备上的返回键，返回到原始存储应用程序。</span><span class="sxs-lookup"><span data-stu-id="633ab-109">When a user is done editing a file, they can choose the back key on the device to return to the original storage application.</span></span>
  
## <a name="verify-that-office-has-been-installed"></a><span data-ttu-id="633ab-110">确定已安装 Office</span><span class="sxs-lookup"><span data-stu-id="633ab-110">Verify that Office has been installed</span></span>

<span data-ttu-id="633ab-p104">引用的应用程序将首先需要验证特定 Office 应用程序是否已安装。以下 Office 应用程序可以安装在 Android 设备上用于查看和编辑文档：</span><span class="sxs-lookup"><span data-stu-id="633ab-p104">Your referring application will first need to verify that a particular Office application is installed. The following Office applications can be installed on Android devices for document viewing and editing:</span></span> 
  
- <span data-ttu-id="633ab-113">Excel</span><span class="sxs-lookup"><span data-stu-id="633ab-113">Excel</span></span>
    
- <span data-ttu-id="633ab-114">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="633ab-114">PowerPoint</span></span>
    
- <span data-ttu-id="633ab-115">Word</span><span class="sxs-lookup"><span data-stu-id="633ab-115">Word</span></span>
    
<span data-ttu-id="633ab-p105">使用 Android PackageManager 确定设备上是否已安装特定的 Office 应用程序。下表列出了您在此过程中可使用的 Office 应用程序包的名称。</span><span class="sxs-lookup"><span data-stu-id="633ab-p105">Use Android PackageManager to determine whether a particular Office application is installed on the device. The following table lists the package names for the Office applications that you can use in this process.</span></span>
  
|<span data-ttu-id="633ab-118">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="633ab-118">**Application**</span></span>|<span data-ttu-id="633ab-119">**包名称**</span><span class="sxs-lookup"><span data-stu-id="633ab-119">**Package name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="633ab-120">Excel</span><span class="sxs-lookup"><span data-stu-id="633ab-120">Excel</span></span>  <br/> |<span data-ttu-id="633ab-121">com.microsoft.office.excel</span><span class="sxs-lookup"><span data-stu-id="633ab-121">com.microsoft.office.excel</span></span>  <br/> |
|<span data-ttu-id="633ab-122">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="633ab-122">PowerPoint</span></span>  <br/> |<span data-ttu-id="633ab-123">com.microsoft.office.powerpoint</span><span class="sxs-lookup"><span data-stu-id="633ab-123">com.microsoft.office.powerpoint</span></span>  <br/> |
|<span data-ttu-id="633ab-124">Word</span><span class="sxs-lookup"><span data-stu-id="633ab-124">Word</span></span>  <br/> |<span data-ttu-id="633ab-125">com.microsoft.office.word</span><span class="sxs-lookup"><span data-stu-id="633ab-125">com.microsoft.office.word</span></span>  <br/> |
   
### <a name="prompt-the-user-to-install-office"></a><span data-ttu-id="633ab-126">提示用户安装 Office</span><span class="sxs-lookup"><span data-stu-id="633ab-126">Prompt the user to install Office</span></span>

<span data-ttu-id="633ab-p106">如果未安装某个特定的 Office 应用程序，您可以提示用户安装该应用程序。下表列出了 Office 应用程序可用的安装位置。</span><span class="sxs-lookup"><span data-stu-id="633ab-p106">If a particular Office application is not installed, you can prompt the user to install the application. The following table lists the available install locations for Office applications.</span></span>
  
|<span data-ttu-id="633ab-129">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="633ab-129">**Application**</span></span>|<span data-ttu-id="633ab-130">**Google Play 商店**</span><span class="sxs-lookup"><span data-stu-id="633ab-130">**Google Play Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="633ab-131">Excel</span><span class="sxs-lookup"><span data-stu-id="633ab-131">Excel</span></span>  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.excel](https://play.google.com/store/apps/details?id=com.microsoft.office.excel) <br/> |
|<span data-ttu-id="633ab-132">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="633ab-132">PowerPoint</span></span>  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint](https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint) <br/> |
|<span data-ttu-id="633ab-133">Word</span><span class="sxs-lookup"><span data-stu-id="633ab-133">Word</span></span>  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.word](https://play.google.com/store/apps/details?id=com.microsoft.office.word) <br/> |
   
## <a name="invoke-office"></a><span data-ttu-id="633ab-134">调用 Office</span><span class="sxs-lookup"><span data-stu-id="633ab-134">Invoke Office</span></span>

<span data-ttu-id="633ab-135">当安装 Office 应用程序时，引用应用程序可以通过传递以下详细信息调用 Office：</span><span class="sxs-lookup"><span data-stu-id="633ab-135">When the Office application is installed, your referring application can invoke Office by passing the following details:</span></span>
  
- <span data-ttu-id="633ab-136">Office 协议</span><span class="sxs-lookup"><span data-stu-id="633ab-136">Office protocol</span></span>
    
- <span data-ttu-id="633ab-137">打开模式</span><span class="sxs-lookup"><span data-stu-id="633ab-137">Open mode</span></span>
    
- <span data-ttu-id="633ab-138">URL</span><span class="sxs-lookup"><span data-stu-id="633ab-138">URL</span></span>
    
<span data-ttu-id="633ab-139">架构格式：</span><span class="sxs-lookup"><span data-stu-id="633ab-139">Schema format:</span></span>
  
 `<Office protocol><open mode>|u|<URL>`
  
<span data-ttu-id="633ab-140">以下示例显示调用 Word 文件以供编辑的请求。</span><span class="sxs-lookup"><span data-stu-id="633ab-140">The following example shows a request to invoke a Word file for editing.</span></span>
  
 `ms-word:ofe|u|https://contoso/Q4/budget.docx`
  
### <a name="office-protocols"></a><span data-ttu-id="633ab-141">Office 协议</span><span class="sxs-lookup"><span data-stu-id="633ab-141">Office protocols</span></span>

<span data-ttu-id="633ab-142">下表列出了每个 Office 应用程序的协议。</span><span class="sxs-lookup"><span data-stu-id="633ab-142">The following table lists the protocols for each Office application.</span></span>
  
|<span data-ttu-id="633ab-143">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="633ab-143">**Application**</span></span>|<span data-ttu-id="633ab-144">**协议**</span><span class="sxs-lookup"><span data-stu-id="633ab-144">**Protocol**</span></span>|
|:-----|:-----|
|<span data-ttu-id="633ab-145">Excel</span><span class="sxs-lookup"><span data-stu-id="633ab-145">Excel</span></span>  <br/> |<span data-ttu-id="633ab-146">ms-excel:</span><span class="sxs-lookup"><span data-stu-id="633ab-146">ms-excel:</span></span>  <br/> |
|<span data-ttu-id="633ab-147">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="633ab-147">PowerPoint</span></span>  <br/> |<span data-ttu-id="633ab-148">ms-powerpoint:</span><span class="sxs-lookup"><span data-stu-id="633ab-148">ms-powerpoint:</span></span>  <br/> |
|<span data-ttu-id="633ab-149">Word</span><span class="sxs-lookup"><span data-stu-id="633ab-149">Word</span></span>  <br/> |<span data-ttu-id="633ab-150">ms-word:</span><span class="sxs-lookup"><span data-stu-id="633ab-150">ms-word:</span></span>  <br/> |
   
### <a name="open-mode"></a><span data-ttu-id="633ab-151">打开模式</span><span class="sxs-lookup"><span data-stu-id="633ab-151">Open mode</span></span>

<span data-ttu-id="633ab-p107">Office 应用程序可以直接在视图 (ofv) 或编辑 (ofe) 模式下打开文件。编辑模式为默认设置。</span><span class="sxs-lookup"><span data-stu-id="633ab-p107">Office applications can open files directly into view (ofv) or edit (ofe) mode. Edit mode is the default.</span></span>
  
<span data-ttu-id="633ab-154">架构格式：</span><span class="sxs-lookup"><span data-stu-id="633ab-154">Schema format:</span></span>
  
 `<ofv or ofe>`
  
### <a name="url"></a><span data-ttu-id="633ab-155">URL</span><span class="sxs-lookup"><span data-stu-id="633ab-155">URL</span></span>

<span data-ttu-id="633ab-156">URL 包括三个部分：</span><span class="sxs-lookup"><span data-stu-id="633ab-156">The URL includes three parts:</span></span>
  
- <span data-ttu-id="633ab-157">文件将在编辑 (ofe) 模式下打开的声明</span><span class="sxs-lookup"><span data-stu-id="633ab-157">The declaration that the file will be opened for edit (ofe)</span></span>
    
- <span data-ttu-id="633ab-158">URL 描述符 (|u|)</span><span class="sxs-lookup"><span data-stu-id="633ab-158">The URL descriptor (|u|)</span></span>
    
- <span data-ttu-id="633ab-159">URL</span><span class="sxs-lookup"><span data-stu-id="633ab-159">The URL</span></span>
    
<span data-ttu-id="633ab-p108">URL 必须进行编码，并且必须是指向文件（不是重定向）的直接链接。如果 URL 的格式不是 Office 能够处理的格式，或者只是下载失败，Office 就不会将用户返回到调用应用程序。</span><span class="sxs-lookup"><span data-stu-id="633ab-p108">The URL has to be encoded and must be a direct link to the file (not a redirect). If the URL is in a format that Office cannot handle, or the download simply fails, Office will not return the user to the invoking application.</span></span>
  
<span data-ttu-id="633ab-162">架构格式：</span><span class="sxs-lookup"><span data-stu-id="633ab-162">Schema format:</span></span>
  
 `|u|<document URL>`
  
## <a name="see-also"></a><span data-ttu-id="633ab-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="633ab-163">See also</span></span>
<span data-ttu-id="633ab-164"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="633ab-164"><a name="bk_addresources"> </a></span></span>

- [<span data-ttu-id="633ab-165">与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="633ab-165">Integrate with Office</span></span>](integrate-with-office.md)
    
- [<span data-ttu-id="633ab-166">PackageManager</span><span class="sxs-lookup"><span data-stu-id="633ab-166">PackageManager</span></span>](https://developer.android.com/reference/android/content/pm/PackageManager.html)
    
- [<span data-ttu-id="633ab-167">GetPackageManager()</span><span class="sxs-lookup"><span data-stu-id="633ab-167">GetPackageManager()</span></span>](https://developer.android.com/reference/android/content/Context.html)
    

