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
# <a name="integrate-with-office-from-android-applications"></a>从 Android 应用程序与 Office 集成

Office for Android 提供了一个可扩展的的解决方案，可与第三方应用程序集成。您可以将用户从您的应用程序传递到 Office，从 Android 应用程序与 Office 集成。
  
您可以让在 Android 设备上运行 Office 的用户从任何应用程序打开和编辑存储在 SharePoint 或 OneDrive 中的文件。为此，您可以通过协议处理程序将文件传递到 Office，并确保以 Office 可以理解的方式来调用 Office。
  
用户完成编辑文件后，可以选择设备上的返回键，返回到原始存储应用程序。
  
## <a name="verify-that-office-has-been-installed"></a>确定已安装 Office

引用的应用程序将首先需要验证特定 Office 应用程序是否已安装。以下 Office 应用程序可以安装在 Android 设备上用于查看和编辑文档： 
  
- Excel
    
- PowerPoint
    
- Word
    
使用 Android PackageManager 确定设备上是否已安装特定的 Office 应用程序。下表列出了您在此过程中可使用的 Office 应用程序包的名称。
  
|**Application**|**包名称**|
|:-----|:-----|
|Excel  <br/> |com.microsoft.office.excel  <br/> |
|PowerPoint  <br/> |com.microsoft.office.powerpoint  <br/> |
|Word  <br/> |com.microsoft.office.word  <br/> |
   
### <a name="prompt-the-user-to-install-office"></a>提示用户安装 Office

如果未安装某个特定的 Office 应用程序，您可以提示用户安装该应用程序。下表列出了 Office 应用程序可用的安装位置。
  
|**应用程序**|**Google Play 商店**|
|:-----|:-----|
|Excel  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.excel](https://play.google.com/store/apps/details?id=com.microsoft.office.excel) <br/> |
|PowerPoint  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint](https://play.google.com/store/apps/details?id=com.microsoft.office.powerpoint) <br/> |
|Word  <br/> |[https://play.google.com/store/apps/details?id=com.microsoft.office.word](https://play.google.com/store/apps/details?id=com.microsoft.office.word) <br/> |
   
## <a name="invoke-office"></a>调用 Office

当安装 Office 应用程序时，引用应用程序可以通过传递以下详细信息调用 Office：
  
- Office 协议
    
- 打开模式
    
- URL
    
架构格式：
  
 `<Office protocol><open mode>|u|<URL>`
  
以下示例显示调用 Word 文件以供编辑的请求。
  
 `ms-word:ofe|u|https://contoso/Q4/budget.docx`
  
### <a name="office-protocols"></a>Office 协议

下表列出了每个 Office 应用程序的协议。
  
|**应用程序**|**协议**|
|:-----|:-----|
|Excel  <br/> |ms-excel:  <br/> |
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
  
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [与 Office 集成](integrate-with-office.md)
    
- [PackageManager](https://developer.android.com/reference/android/content/pm/PackageManager.html)
    
- [GetPackageManager()](https://developer.android.com/reference/android/content/Context.html)
    

