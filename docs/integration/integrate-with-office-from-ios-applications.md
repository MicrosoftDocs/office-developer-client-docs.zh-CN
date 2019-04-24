---
title: 从 iOS 应用程序与 Office 集成
manager: soliver
ms.date: 06/04/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: f3a277ba-7ba1-4eea-83b5-915b409f3093
description: Office for iOS 提供了一个可扩展的解决方案，以便能够与第三方应用程序集成。本文介绍如何从 iOS 应用程序与 Office 集成，如何通过将用户从您的应用程序传递到 Office 然后再将他们返回到您的应用程序来实现集成。
ms.openlocfilehash: d17a096c17eadab0cd94ee1dce18e979e80fa65d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299745"
---
# <a name="integrate-with-office-from-ios-applications"></a>从 iOS 应用程序与 Office 集成

Office for iOS 提供了一个可扩展的解决方案，以便能够与第三方应用程序集成。本文介绍如何从 iOS 应用程序与 Office 集成，如何通过将用户从您的应用程序传递到 Office 然后再将他们返回到您的应用程序来实现集成。
  
可以使在 iOS 设备上运行 Office 的用户能够从任何应用程序打开和编辑存储在 SharePoint 或 OneDrive 中的文件，然后在完成编辑文件后快速将其返回到原始应用程序中。若要执行此操作，您可以通过协议处理程序将文件传递到 Office，并确保采用 Office 可以理解的方式来调用 Office。
  
当用户完成了对某个文件的编辑后，假如在 Office 应用程序启动时您将特定信息传递给 了它，则用户可以选择 Office 应用程序中的后退箭头关闭该文档，并返回到原始存储应用程序。
  
## <a name="verify-that-office-has-been-installed"></a>验证是否已安装 Office

引用的应用程序将首先需要验证特定 Office 应用程序是否已安装。以下 Office 应用程序可以安装在 iOS 设备上用于查看和编辑文档：
  
- Excel
    
- OneNote
    
- PowerPoint
    
- Word
    
使用 [canOpenURL](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html) 方法确定您的应用程序是否可以打开资源。此方法将资源的 URL 作为参数，如果接受 URL 的应用程序不可用，则返回 **No**。如果 **canOpenURL** 返回 **No**，则您将需要提示用户安装 Office。
  
### <a name="prompt-the-user-to-install-office"></a>提示用户安装 Office

 如果未安装某个特定 Office 应用程序，您可以使用 [SKProductViewController](https://developer.apple.com/library/ios/documentation/StoreKit/Reference/SKITunesProductViewController_Ref/index.html) 对象，以在您的应用程序中呈现 iTunes 应用商店并向用户显示要安装的 Office 应用程序。下表列出了要用于在商店工具包产品视图控制器中调用每个 Office 应用程序的 iTunes 标识符。 
  
|**Office 应用程序**|**iTunes 标识符**|
|:-----|:-----|
|Excel  <br/> |[https://itunes.apple.com/us/app/microsoft-excel/id586683407?mt=8&amp;uo=4](https://itunes.apple.com/us/app/microsoft-excel/id586683407?mt=8&amp;uo=4) <br/> |
|OneNote (iPhone)  <br/> |[https://itunes.apple.com/us/app/microsoft-onenote-for-iphone/id410395246?mt=8&amp;uo=4](https://itunes.apple.com/us/app/microsoft-onenote-for-iphone/id410395246?mt=8&amp;uo=4) <br/> |
|PowerPoint  <br/> |[https://itunes.apple.com/us/app/microsoft-powerpoint/id586449534?mt=8&amp;uo=4](https://itunes.apple.com/us/app/microsoft-powerpoint/id586449534?mt=8&amp;uo=4) <br/> |
|Word  <br/> |[https://itunes.apple.com/us/app/microsoft-word/id586447913?mt=8&amp;uo=4](https://itunes.apple.com/us/app/microsoft-word/id586447913?mt=8&amp;uo=4) <br/> |
   
## <a name="invoke-office"></a>调用 Office

当安装 Office 应用程序时，引用应用程序可以通过传递以下详细信息调用 Office： 
  
- Office 协议
    
- 打开模式
    
- URL
    
- Passback 协议
    
- 文档上下文
    
架构格式：
  
 `<Office protocol><open mode>|u|<URL>|p|<passback protocol>|c|<document context>`
  
以下示例显示调用 Word 文件以供编辑的请求：
  
 `ms-word:ofe|u|https://contoso/Q4/budget.docx|p|clouddrive|c|folderviewQ4`
  
### <a name="office-protocols"></a>Office 协议

下表列出了每个 Office 应用程序的协议。 
  
|**应用程序**|**协议**|
|:-----|:-----|
|Excel  <br/> |ms-excel:  <br/> |
|OneNote  <br/> |onenote:  <br/> |
|PowerPoint  <br/> |ms-powerpoint:  <br/> |
|Word  <br/> |ms-word:  <br/> |
   
### <a name="open-mode"></a>打开模式

Office 应用程序可以直接在视图 (ofv) 或编辑 (ofe) 模式下打开文件。编辑模式为默认设置。 
  
架构格式：
  
 `<ofv or ofe>`
  
### <a name="url"></a>URL

URL 包括三个部分： 
  
- 文件将在编辑 (ofe) 模式下打开的声明
    
- URL 描述符 (|u|)
    
- URL
    
URL 必须进行编码，并且必须是指向文件（不是重定向）的直接链接。如果 URL 的格式不是 Office 能够处理的格式，或者只是下载失败，Office 就不会将用户返回到调用应用程序。 
  
架构格式：
  
 `|u|<document URL>`
  
### <a name="passback-protocol-optional"></a>Passback 协议（可选）

如果您希望在用户选择后退箭头时，Office 将用户返回到您的 iOS 应用程序，那么调用应用程序将需要使用 passback 协议，包括后接应用程序协议（不带冒号）的描述符"|p|"。您将需要确保您的应用程序可以正确地处理来自 Office 的响应。
  
架构格式：
  
 `|p|<passback protocol>`
  
### <a name="document-context-optional"></a>文档上下文（可选）

Office 不使用文档上下文，但引用应用程序可能在 Office 传递回用户时需要用到它。如果您希望文档上下文返回到您的应用程序，则使用描述符 "|c|"，后接您希望将其作为字符串的上下文。除了由操作系统施加的限制以外，Office 不会限制该字符串的长度。
  
架构格式：
  
 `|c|<document context>`
  
## <a name="return-users-to-the-referring-application"></a>将用户返回到引用应用程序

出于安全考虑，如果文件已成功打开，则 Office 仅将用户返回到引用应用程序。 当用户选择后退箭头，Office 将根据 passback 协议、打开模式、URL、上载待定状态和文档上下文来响应调用应用程序。上载待定状态使用描述符 "|z|"，其值为 "Yes" 或 "No"。
  
架构格式：
  
 `<app protocol>:ofe|u|<URL>|z|<yes or no>|c|<doc context> Example: clouddrive:ofe|u|https://contoso/Q4/budget.docx|z|no|c|folderviewQ4`
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [canOpenURL 方法](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html)
    
- [UIApplication 类](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIApplication_Class/index.html)
    
- [SKProductViewController 对象](https://developer.apple.com/library/ios/documentation/StoreKit/Reference/SKITunesProductViewController_Ref/index.html)
    

