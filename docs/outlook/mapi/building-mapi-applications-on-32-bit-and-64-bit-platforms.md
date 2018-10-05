---
title: 在 32 位和 64 位平台上构建 MAPI 应用程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d218ba2d-7a2e-4c33-a09b-a8c7e27f9726
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bc98b201b31048e22e093d92c9cf2d5ff1fb0257
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383147"
---
# <a name="building-mapi-applications-on-32-bit-and-64-bit-platforms"></a>在 32 位和 64 位平台上构建 MAPI 应用程序

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题介绍以更改并重新构建在 64 位平台上，运行 32 位 MAPI 的应用程序和 64 位应用程序在 32 位平台上运行，MAPI 开发人员应采取的操作。 本主题中的 64 位平台是安装 64 位 Microsoft Outlook 和 64 位 Windows，一台计算机，32 位平台安装 32 位 Outlook 和 32 位或 64 位 Windows 的计算机。 
  
## <a name="operating-system-and-office-support-for-64-bit-outlook"></a>操作系统和 64 位 Outlook 的 Office 支持

> [!NOTE]
> 术语位数指的是 32 位和 64 位处理器体系结构和关联的应用程序兼容性之间的区别。 本主题中 bitness 用于限定 Windows、 Microsoft Office、 Outlook 或 MAPI 应用程序构建以满足计算机的 32 位或 64 位处理器体系结构和可能选择在该计算机运行其他应用程序的版本。 
  
启动 Microsoft Office 2010 中，Outlook 位于为 32 位和 64 位应用程序。 在同一台计算机上，Outlook 位数取决于位数和 Microsoft Office 的 Windows 操作系统 （x86 或 x64），如果已在该计算机上安装 Office。 下面是 outlook 的一些确定安装 32 位或 64 位版本可行的因素：
  
- 32 位 Office（和 32 位 Outlook）可以安装在 32 位或 64 位版本的 Windows 操作系统上。64 位 Office（和 64 位 Outlook）只能安装在 64 位操作系统上。
    
- 在 64 位版本的 Windows 操作系统上，默认安装的 Office 是 32 位 Office。
    
- 位数的安装版本始终是 office 的 outlook 的相同，位数如果同一台计算机上安装 Office。 换句话说，不能在已安装，如 Microsoft Word 64 位或 64 位 Microsoft Excel 其他 Office 应用程序的 64 位版本的同一台计算机上安装 32 位版本的 Outlook。 同样，不能在已安装其他 Office 应用程序的 32 位版本的同一台计算机上安装 64 位版本的 Outlook。
    
## <a name="preparing-mapi-applications-for-32-bit-and-64-bit-platforms"></a>准备用于 32 位和 64 位平台的 MAPI 应用程序

MAPI 应用程序包括独立应用程序，如 Microsoft Communicator 和 MFCMAPI，如通讯簿服务提供程序存储和传输提供程序。 对于 MAPI 方法和函数的 MAPI 应用程序的位数 （除外一个简单 MAPI 函数，MAPISendMail），MAPI 应用程序中单位电话的呼叫必须是相同的到目标应用程序的计算机上的 MAPI 子系统 bitness上运行。 MAPI 子系统位数反过来，取决于通过以及始终安装的 Outlook 版本位数相同。 下表总结了必要的操作以准备使用 Office 和 Windows 的各种 bitness 配置的目标计算机上运行的 MAPI 应用程序。
  
|位元 MAPI 应用程序|在目标计算机上的 Outlook 的位元|在目标计算机上的 Windows 的位元|要启用要在目标计算机上运行的应用程序所需操作|
|:-----|:-----|:-----|:-----|
|32 位  <br/> |32 位  <br/> |32 位或 64 位  <br/> |不不需要任何特定操作。  <br/> |
|32 位  <br/> |64 位  <br/> |64 位  <br/> |重新生成作为 64 位应用程序的应用程序。 否则，（除外**MAPISendMail**) 的所有 MAPI 方法和函数调用将都失败。  <br/> |
|64 位  <br/> |64 位  <br/> |64 位  <br/> |不不需要任何特定操作。  <br/> |
|64 位  <br/> |32 位  <br/> |32 位或 64 位  <br/> |重新生成作为 32 位应用程序的应用程序。 否则，（除外**MAPISendMail**) 的所有 MAPI 方法和函数调用将都失败。  <br/> |
   
以下各节详细介绍每种方案。 需要重建的 MAPI 应用程序的方案，请参阅关于链接到和调用 MAPI 函数的其他信息的[链接到 MAPI 函数](how-to-link-to-mapi-functions.md)。 
  
### <a name="32-bit-mapi-application-and-32-bit-outlook"></a>32 位 MAPI 应用程序和 32 位 Outlook

MAPI 应用程序有 32 位版本的 Outlook，包括 Microsoft Outlook 2013 之前这些版本的 32 位 MAPI 子系统编译继续安装 32 位 Outlook 和 32 位或 64 位 Windows 的计算机上必须支持操作系统。 没有必要的应用程序开发的特定操作。
  
### <a name="32-bit-mapi-application-and-64-bit-outlook"></a>32 位 MAPI 应用程序和 64 位 Outlook

32 位 MAPI 应用程序不支持安装 64 位 Outlook 与 64 位 Windows 的计算机上运行。 应用程序开发人员必须更新并重新生成作为一个用于 64 位平台的 64 位应用程序的应用程序。 这是因为 32 位应用程序无法加载的 64 位 Msmapi32.dll 文件。 有少量 API 应用程序开发人员必须包含构建其代码成功的 64 位环境的更改。 使用这些改变以支持 64 位平台，MAPI 头文件进行了更新。 您可以下载这些头文件在[Outlook 2010: MAPI 头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)。 开发人员可以使用此一组相同的 MAPI 头文件来构建 32 位和 64 位的 MAPI 应用程序。
  
### <a name="64-bit-mapi-application-and-64-bit-outlook"></a>64 位 MAPI 应用程序和 64 位 Outlook

64 位 MAPI 应用程序支持安装 64 位 Outlook 和 64 位 Windows 的计算机上。 没有必要的应用程序开发的特定操作。
  
### <a name="64-bit-mapi-application-and-32-bit-outlook"></a>64 位 MAPI 应用程序和 32 位 Outlook

64 位 MAPI 应用程序不支持在安装 32 位 Outlook 和 32 位或 64 位 Windows 计算机上运行。 应用程序开发人员必须更新并重新生成作为 32 位应用程序以使用 32 位 Outlook 应用程序。 使用更新的 MAPI 头文件，可以在下载[Outlook 2010: MAPI 头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)。 开发人员可以使用此一组相同的 MAPI 头文件来构建 32 位和 64 位的 MAPI 应用程序。
  
### <a name="exception-mapisendmail"></a>异常： MAPISendMail

一般情况下，32 位 MAPI 应用程序必须在上运行 64 位平台 (64 位 Windows 上的 64 位 Outlook) 而无需第一个成为重建与 32 位 Outlook 安装的计算机上未运行 64 位应用程序和 64 位 MAPI 应用程序，必须如和 32 位或 64 位Windows 事先重建作为 32 位应用程序。 图 1 显示了是否发生这些方案之一，将显示警报对话框。
  
**图 1。错误消息的大部分跨位元 MAPI 调用。**

![用于大部分跨位元 MAPI 调用的错误消息](media/738905fb-57ae-4af7-b54b-a1676c80d3c3.JPG "用于大部分跨位元 MAPI 调用的错误消息")
  
但是，将在所有简单 MAPI 和 MAPI 元素， **MAPISendMail**，之间的一个函数调用成功 Windows-32-bit-on-Windows-64-bit (WOW64) 或 Windows-64-bit-on-Windows-32-bit (WOW32) 方案中，不会导致上面的通知。 此 WOW64 方案仅适用于 Windows 7。 

图 2 显示了其中的 32 位 MAPI 应用程序安装与 64 位 Windows 7 的计算机调用**MAPISendMail** WOW64 方案。 在此方案中，MAPI 库进行 COM 调用启动 64-bit Fixmapi 应用程序。 到 MAPI 库中，将路由到 Windows MAPI 存根，又将转发到 Outlook MAPI 存根，启用**MAPISendMail**函数调用成功调用的函数调用隐式链接 Fixmapi 应用程序。 
  
**图 2。WOW64 方案中处理 MAPISendMail。**

![WOW64 方案中处理 MAPISendMail](media/346ba974-4844-4b64-9dd1-d0f829ab99b3.gif "WOW64 方案中处理 MAPISendMail")
  
## <a name="see-also"></a>另请参阅

- [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)

