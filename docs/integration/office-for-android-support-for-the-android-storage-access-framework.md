---
title: Android 存储访问框架的 Office for Android 支持
manager: soliver
ms.date: 06/18/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cfed295-f499-44dc-bac5-9e266df1b5b3
description: Office for Android 与 Android 存储访问框架集成，使 Office 能够打开其他文档提供程序存储的文件。
ms.openlocfilehash: 24d7e48106aeb5e58a668b94cbde00eaa9175230
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300348"
---
# <a name="office-for-android-support-for-the-android-storage-access-framework"></a>Android 存储访问框架的 Office for Android 支持

Office for Android 与 Android 存储访问框架集成，使 Office 能够打开其他文档提供程序存储的文件。
  
Android 4.4（API 级别 19）引入了存储访问框架 (SAF)。SAF 使用户可以跨所有首选的文档存储提供程序浏览和打开文档、图像和其他文件。标准的 UI 使用户能够跨应用程序和提供程序以一致的方式浏览文件和访问文件。
  
## <a name="implement-a-document-provider"></a>实现文档提供程序

如果您正在开发提供文档存储服务的应用，可通过[编写自定义文档提供程序](https://developer.android.com/guide/topics/providers/document-provider.html)的方式借助 SAF 来提供文件。之后，Office 应用就可以调用 [ACTION_OPEN_DOCUMENT](https://developer.android.com/reference/android/content/Intent.html) 和/或 [ACTION_CREATE_DOCUMENT](https://developer.android.com/reference/android/content/Intent.html)，以便能够收到文档提供程序返回的文件。请注意，此做法可能要加入一些筛选器来进一步优化条件。 
  
## <a name="enable-free-consumer-edits"></a>启用免费使用者编辑

用户可以使用免费的 Microsoft 帐户登录 Office 应用，以创建或编辑面向用户的存储服务中存储的文档。下表列出了提供程序必须提供作为光标组成部分的强制属性，通过存储访问框架启用文档的免费使用者编辑。
  
|**属性**|**Index**|**值**|
|:-----|:-----|:-----|
|文档类型  <br/> |com_microsoft_office_doctype  <br/> |\<使用者\>  <br/> |
|服务友好名称  <br/> |com_microsoft_office_servicename  <br/> |服务的任何用户友好名称，可用于标识 Office 应用的"最近使用的文件"列表中的文档。请注意，在显示服务的友好名称之前，必须提供"使用协议条款"属性。  <br/> |
|使用协议条款  <br/> |com_microsoft_office_termsofuse  <br/> |\<我同意接受以下位置上列出的条款：https://go.microsoft.com/fwlink/p/?LinkId=528381\>  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="bk_addresources"> </a>

- [与 Office 集成](integrate-with-office.md)
    
- [内容提供程序基础知识](hhttps://developer.android.com/guide/topics/providers/content-provider-basics.html)
    
- [创建内容提供程序](https://developer.android.com/guide/topics/providers/content-provider-creating.html)
    
- [存储访问框架开发人员指南](https://developer.android.com/guide/topics/providers/document-provider.html)
    

