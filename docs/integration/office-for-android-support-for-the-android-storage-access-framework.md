---
title: Android 存储访问框架的 Office for Android 支持
manager: soliver
ms.date: 06/18/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cfed295-f499-44dc-bac5-9e266df1b5b3
description: Office for Android 与 Android 存储访问框架集成，使 Office 能够打开其他文档提供程序存储的文件。
ms.openlocfilehash: 24d7e48106aeb5e58a668b94cbde00eaa9175230
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384547"
---
# <a name="office-for-android-support-for-the-android-storage-access-framework"></a><span data-ttu-id="18eae-103">Android 存储访问框架的 Office for Android 支持</span><span class="sxs-lookup"><span data-stu-id="18eae-103">Office for Android support for the Android Storage Access Framework</span></span>

<span data-ttu-id="18eae-104">Office for Android 与 Android 存储访问框架集成，使 Office 能够打开其他文档提供程序存储的文件。</span><span class="sxs-lookup"><span data-stu-id="18eae-104">Office for Android integrates with the Android Storage Access Framework, which enables Office to open files stored by another document provider.</span></span>
  
<span data-ttu-id="18eae-p101">Android 4.4（API 级别 19）引入了存储访问框架 (SAF)。SAF 使用户可以跨所有首选的文档存储提供程序浏览和打开文档、图像和其他文件。标准的 UI 使用户能够跨应用程序和提供程序以一致的方式浏览文件和访问文件。</span><span class="sxs-lookup"><span data-stu-id="18eae-p101">Android 4.4 (API level 19) introduces the Storage Access Framework (SAF). The SAF enables users to browse and open documents, images, and other files across all their preferred document storage providers. A standard UI lets users browse files and access them in a consistent way across apps and providers.</span></span>
  
## <a name="implement-a-document-provider"></a><span data-ttu-id="18eae-108">实现文档提供程序</span><span class="sxs-lookup"><span data-stu-id="18eae-108">Implement a document provider</span></span>

<span data-ttu-id="18eae-p102">如果您正在开发提供文档存储服务的应用，可通过[编写自定义文档提供程序](https://developer.android.com/guide/topics/providers/document-provider.html)的方式借助 SAF 来提供文件。之后，Office 应用就可以调用 [ACTION_OPEN_DOCUMENT](https://developer.android.com/reference/android/content/Intent.html) 和/或 [ACTION_CREATE_DOCUMENT](https://developer.android.com/reference/android/content/Intent.html)，以便能够收到文档提供程序返回的文件。请注意，此做法可能要加入一些筛选器来进一步优化条件。</span><span class="sxs-lookup"><span data-stu-id="18eae-p102">If you're developing an app that provides storage services for documents, you can make your files available through the SAF by [writing a custom document provider](https://developer.android.com/guide/topics/providers/document-provider.html). Office apps can then invoke the [ACTION_OPEN_DOCUMENT](https://developer.android.com/reference/android/content/Intent.html) and/or [ACTION_CREATE_DOCUMENT](https://developer.android.com/reference/android/content/Intent.html) intent to receive the files returned by your document provider. Note that the intent might include filters to further refine the criteria.</span></span> 
  
## <a name="enable-free-consumer-edits"></a><span data-ttu-id="18eae-112">启用免费使用者编辑</span><span class="sxs-lookup"><span data-stu-id="18eae-112">Enable free consumer edits</span></span>

<span data-ttu-id="18eae-p103">用户可以使用免费的 Microsoft 帐户登录 Office 应用，以创建或编辑面向用户的存储服务中存储的文档。下表列出了提供程序必须提供作为光标组成部分的强制属性，通过存储访问框架启用文档的免费使用者编辑。</span><span class="sxs-lookup"><span data-stu-id="18eae-p103">Users can sign in to the Office apps with a free Microsoft account to create or edit docs that are stored in a consumer-oriented storage service. The following table lists the mandatory properties that providers must supply as part of the cursor, to enable free consumer edit for documents accessed via the Storage Access Framework.</span></span>
  
|<span data-ttu-id="18eae-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="18eae-115">**Property**</span></span>|<span data-ttu-id="18eae-116">**Index**</span><span class="sxs-lookup"><span data-stu-id="18eae-116">**Index**</span></span>|<span data-ttu-id="18eae-117">**值**</span><span class="sxs-lookup"><span data-stu-id="18eae-117">**Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="18eae-118">文档类型</span><span class="sxs-lookup"><span data-stu-id="18eae-118">Document Type</span></span>  <br/> |<span data-ttu-id="18eae-119">com_microsoft_office_doctype</span><span class="sxs-lookup"><span data-stu-id="18eae-119">com_microsoft_office_doctype</span></span>  <br/> |<span data-ttu-id="18eae-120">\<使用者\></span><span class="sxs-lookup"><span data-stu-id="18eae-120">\<consumer\></span></span>  <br/> |
|<span data-ttu-id="18eae-121">服务友好名称</span><span class="sxs-lookup"><span data-stu-id="18eae-121">Service Friendly Name</span></span>  <br/> |<span data-ttu-id="18eae-122">com_microsoft_office_servicename</span><span class="sxs-lookup"><span data-stu-id="18eae-122">com_microsoft_office_servicename</span></span>  <br/> |<span data-ttu-id="18eae-p104">服务的任何用户友好名称，可用于标识 Office 应用的"最近使用的文件"列表中的文档。请注意，在显示服务的友好名称之前，必须提供"使用协议条款"属性。</span><span class="sxs-lookup"><span data-stu-id="18eae-p104">Any user-friendly name for the service, used to identify a document in the Recent list in the Office apps. Note that the "Terms of Use Agreement" property must be supplied before the friendly name for the service can be displayed.</span></span>  <br/> |
|<span data-ttu-id="18eae-125">使用协议条款</span><span class="sxs-lookup"><span data-stu-id="18eae-125">Terms of Use Agreement</span></span>  <br/> |<span data-ttu-id="18eae-126">com_microsoft_office_termsofuse</span><span class="sxs-lookup"><span data-stu-id="18eae-126">com_microsoft_office_termsofuse</span></span>  <br/> |<span data-ttu-id="18eae-127">\<我同意接受以下位置上列出的条款：https://go.microsoft.com/fwlink/p/?LinkId=528381\></span><span class="sxs-lookup"><span data-stu-id="18eae-127">\<I agree to the terms located at https://go.microsoft.com/fwlink/p/?LinkId=528381\></span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="18eae-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18eae-128">See also</span></span>
<span data-ttu-id="18eae-129"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="18eae-129"><a name="bk_addresources"> </a></span></span>

- [<span data-ttu-id="18eae-130">与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="18eae-130">Integrate with Office</span></span>](integrate-with-office.md)
    
- [<span data-ttu-id="18eae-131">内容提供程序基础知识</span><span class="sxs-lookup"><span data-stu-id="18eae-131">Content Provider Basics</span></span>](hhttps://developer.android.com/guide/topics/providers/content-provider-basics.html)
    
- [<span data-ttu-id="18eae-132">创建内容提供程序</span><span class="sxs-lookup"><span data-stu-id="18eae-132">Creating a Content Provider</span></span>](https://developer.android.com/guide/topics/providers/content-provider-creating.html)
    
- [<span data-ttu-id="18eae-133">存储访问框架开发人员指南</span><span class="sxs-lookup"><span data-stu-id="18eae-133">Storage Access Framework Developer Guide</span></span>](https://developer.android.com/guide/topics/providers/document-provider.html)
    

