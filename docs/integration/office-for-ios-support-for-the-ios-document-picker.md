---
title: IOS 文档选取器的 Office for iOS 支持
manager: soliver
ms.date: 02/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 802224ef-6eea-4929-824c-507da1c073a5
description: Office for iOS 与 iOS 文档选取器通过文档提供程序扩展进行集成，使 Office 能够打开另一个文档提供程序存储的文件。
ms.openlocfilehash: 101e3cc248f994fe449a74c6c37f788fad8beed5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774136"
---
# <a name="office-for-ios-support-for-the-ios-document-picker"></a><span data-ttu-id="2fa73-103">IOS 文档选取器的 Office for iOS 支持</span><span class="sxs-lookup"><span data-stu-id="2fa73-103">Office for iOS support for the iOS Document Picker</span></span>

<span data-ttu-id="2fa73-104">Office for iOS 与 iOS 文档选取器通过文档提供程序扩展进行集成，使 Office 能够打开另一个文档提供程序存储的文件。</span><span class="sxs-lookup"><span data-stu-id="2fa73-104">Office for iOS integrates with the iOS Document Picker by means of the Document Provider extension, which enables Office to open files stored by another document provider.</span></span>
  
<span data-ttu-id="2fa73-p101">从 iOS 8.0 开始的 Apple iOS 版本都包括[应用程序扩展支持](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/index.html#//apple_ref/doc/uid/TP40014214-CH20-SW1)。可以使用这些扩展将您的应用程序功能扩展到其他应用程序或用户设备的上下文中。若要将 Office for iOS 与 iOS 文档选取器集成在一起，您可以使用[文档提供程序扩展](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/FileProvider.html)。</span><span class="sxs-lookup"><span data-stu-id="2fa73-p101">Versions of the Apple iOS starting with iOS 8.0 include [app extension support](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/index.html#//apple_ref/doc/uid/TP40014214-CH20-SW1). You can use these extensions to expand the functionality of your application into other apps or contexts on the user's device. To integrate Office for iOS with the iOS Document Picker, you use the [Document Provider extension](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/FileProvider.html).</span></span>
  
<span data-ttu-id="2fa73-108">文档提供程序扩展支持以下四个操作：</span><span class="sxs-lookup"><span data-stu-id="2fa73-108">The Document Provider extension supports four operations:</span></span>
  
- <span data-ttu-id="2fa73-109">导入</span><span class="sxs-lookup"><span data-stu-id="2fa73-109">Import</span></span>
    
- <span data-ttu-id="2fa73-110">导出</span><span class="sxs-lookup"><span data-stu-id="2fa73-110">Export</span></span>
    
- <span data-ttu-id="2fa73-111">打开</span><span class="sxs-lookup"><span data-stu-id="2fa73-111">Open</span></span>
    
- <span data-ttu-id="2fa73-112">移动</span><span class="sxs-lookup"><span data-stu-id="2fa73-112">Move</span></span>
    
<span data-ttu-id="2fa73-p102">Office for iOS 与打开操作集成。当您创建了文档提供程序扩展时，您的用户可以使用文档选取器直接在 Office 中打开和编辑文档，无需创建该文件的副本。</span><span class="sxs-lookup"><span data-stu-id="2fa73-p102">Office for iOS integrates with the open operation. When you create a Document Provider extension, your users can use the Document Picker to open and edit documents directly in Office without creating a duplicate copy of the file.</span></span>
  
## <a name="learn-more-about-app-extensions-and-the-document-picker"></a><span data-ttu-id="2fa73-115">了解有关应用程序扩展和文档选取器的详细信息</span><span class="sxs-lookup"><span data-stu-id="2fa73-115">Learn more about app extensions and the Document Picker</span></span>
<span data-ttu-id="2fa73-116"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="2fa73-116"></span></span>

- [<span data-ttu-id="2fa73-117">应用程序扩展</span><span class="sxs-lookup"><span data-stu-id="2fa73-117">App extensions</span></span>](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/index.html#//apple_ref/doc/uid/TP40014214-CH20-SW1)
    
- [<span data-ttu-id="2fa73-118">文档选取器编程指南</span><span class="sxs-lookup"><span data-stu-id="2fa73-118">Document Picker Programming Guide</span></span>](https://developer.apple.com/library/prerelease/ios/documentation/FileManagement/Conceptual/DocumentPickerProgrammingGuide/Introduction/Introduction.html)
    
- [<span data-ttu-id="2fa73-119">文档提供程序编程指南</span><span class="sxs-lookup"><span data-stu-id="2fa73-119">Document Provider Programming Guide</span></span>](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/FileProvider.html)
    

