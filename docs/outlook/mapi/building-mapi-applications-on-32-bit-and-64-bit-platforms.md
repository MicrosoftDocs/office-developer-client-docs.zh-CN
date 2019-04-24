---
title: 在 32 位和 64 位平台上生成 MAPI 应用程序
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
api_type:
- COM
ms.assetid: d218ba2d-7a2e-4c33-a09b-a8c7e27f9726
description: 上次修改时间：2015 年 3 月 9 日
localization_priority: Priority
ms.openlocfilehash: 74f321d2c6c8b5159191d4dcdb62e0db21132435
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326462"
---
# <a name="building-mapi-applications-on-32-bit-and-64-bit-platforms"></a>在 32 位和 64 位平台上生成 MAPI 应用程序

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题介绍了 MAPI 开发人员更改和重新生成在 64 位平台上运行的 32 位 MAPI 应用程序以及在 32 位平台上运行的 64 位应用程序所需采取的操作。 在本主题中，64 位平台为安装了 64 位 Microsoft Outlook 和 64 位 Windows 的计算机，32 位平台为安装了 32 位 Outlook 和 32 位或 64 位 Windows 的计算机。 
  
## <a name="operating-system-and-office-support-for-64-bit-outlook"></a>64 位 Outlook 的操作系统和 Office 支持

> [!NOTE]
> 术语“位数”是指 32 位和 64 位处理器体系结构与应用程序的相关兼容性之间的区别。 在本主题中，位数用于限定适用于计算机的 32 位或 64 位处理器体系结构的 Windows、Microsoft Office、Outlook 或 MAPI 应用程序或者在该计算机上运行的其他可能应用程序的版本。 
  
从 Microsoft Office 2010 起，Outlook 提供有 32 位和 64 位应用程序。 在同一台计算机上，Outlook 的位数取决于 Windows 操作系统（x86 或 x64）的位数和 Microsoft Office 的位数（如该计算机上已安装 Office）。 以下是部分确定安装 32 位或 64 位版本 Outlook 是否可行的因素：
  
- 32 位 Office（和 32 位 Outlook）可以安装在 32 位或 64 位版本的 Windows 操作系统上。64 位 Office（和 64 位 Outlook）只能安装在 64 位操作系统上。
    
- 在 64 位版本的 Windows 操作系统上，默认安装的是 32 位 Office。
    
- 如果在同一计算机上安装了 Office，则已安装的 Outlook 版本的位数始终与 Office 的位数相同。 换而言之，在已安装 64 位版本的其他 Office 应用程序（如 64 位 Microsoft Word 或 64 位 Microsoft Excel）的同一计算机上，无法安装 32 位版本的 Outlook。 同样，64 位版本的 Outlook 不能安装在已安装 32 位版本的其他 Office 应用程序的同一台计算机上。
    
## <a name="preparing-mapi-applications-for-32-bit-and-64-bit-platforms"></a>在 32 位和 64 位平台上准备 MAPI 应用程序

MAPI 应用程序包括独立应用程序（如 Microsoft Communicator 和 MFCMAPI）以及服务提供程序（如通讯簿、存储和传输提供程序）。 若要使 MAPI 方法和函数调用在 MAPI 应用程序中工作（对于一个简单 MAPI 函数 MAPISendMail 则例外），MAPI 应用程序的位数必须与要在其上运行该应用程序的计算机上 MAPI 子系统的位数相同。 而 MAPI 子系统的位数由已安装的 Outlook 版本的位数决定并始终与其相同。 下表汇总了准备 MAPI 应用程序以在不同位数的 Office 和 Windows 配置的目标计算机上运行所需的操作。
  
|MAPI 应用程序的位数|目标计算机上的 Outlook 位数|目标计算机上的 Windows 位数|支持应用程序在目标计算机上运行所需的操作|
|:-----|:-----|:-----|:-----|
|32 位  <br/> |32 位  <br/> |32 位或 64 位  <br/> |不需要任何特定操作。  <br/> |
|32 位  <br/> |64 位  <br/> |64 位  <br/> |将应用程序重新生成为 64 位应用程序。 否则，所有 MAPI 方法和函数调用（**MAPISendMail** 除外）将失败。  <br/> |
|64 位  <br/> |64 位  <br/> |64 位  <br/> |不需要任何特定操作。  <br/> |
|64 位  <br/> |32 位  <br/> |32 位或 64 位  <br/> |将应用程序重新生成为 32 位应用程序。 否则，所有 MAPI 方法和函数调用（**MAPISendMail** 除外）将失败。  <br/> |
   
下面的部分详细介绍了各种应用场景。 对于需要重新生成 MAPI 应用程序的应用场景，请参阅 [MAPI 函数链接](how-to-link-to-mapi-functions.md)，以获取与链接和调用 MAPI 函数相关的其他信息。 
  
### <a name="32-bit-mapi-application-and-32-bit-outlook"></a>32 位 MAPI 应用程序和 32 位 Outlook

在安装了 32 位 Outlook 和 32 位或 64 位 Windows 操作系统的计算机上，仍继续支持针对 32 位版本 Outlook（包括 Microsoft Outlook 2013 之前的版本）中提供的 32 位 MAPI 子系统编译的 MAPI 应用程序。 应用程序开发人员无需采取任何特定操作。
  
### <a name="32-bit-mapi-application-and-64-bit-outlook"></a>32 位 MAPI 应用程序和 64 位 Outlook

在已安装了 64 位 Outlook 和 64 位 Windows 的计算机上不支持运行 32 位 MAPI 应用程序。 应用程序开发人员必须将应用程序更新和重新生成为适合于 64 位平台的 64 位应用程序。 这是因为 32 位应用程序无法加载 64 位 Msmapi32.dll 文件。 若要成功生成适合于 64 位环境的代码，应用程序开发人员必须在其中包含少量 API 更改。 MAPI 头文件已使用这些更改更新，以支持 64 位平台。 你可以在 [Outlook 2010：MAPI 头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)中下载这些头文件。 开发人员可以使用相同的 MAPI 头文件集生成 32 位和 64 位 MAPI 应用程序。
  
### <a name="64-bit-mapi-application-and-64-bit-outlook"></a>64 位 MAPI 应用程序和 64 位 Outlook

在已安装了 64 位 Outlook 和 64 位 Windows 的计算机上支持运行 64 位 MAPI 应用程序。 应用程序开发人员无需采取任何特定操作。
  
### <a name="64-bit-mapi-application-and-32-bit-outlook"></a>64 位 MAPI 应用程序和 32 位 Outlook

在已安装了 32 位 Outlook 和 32 位或 64 位 Windows 的计算机上不支持运行 64 位 MAPI 应用程序。 应用程序开发人员必须将应用程序更新和重新生成为 32 位应用程序才能使用 32 位 Outlook。 使用更新后的 MAPI 头文件，可在 [Outlook 2010：MAPI 头文件](https://www.microsoft.com/downloads/details.aspx?FamilyID=f8d01fc8-f7b5-4228-baa3-817488a66db1)中下载该文件。 开发人员可以使用相同的 MAPI 头文件集生成 32 位和 64 位 MAPI 应用程序。
  
### <a name="exception-mapisendmail"></a>例外：MAPISendMail

一般情况下，如果没有先重新生成为 64 位应用程序，则 32 位 MAPI 应用程序不能在 64 位平台（64 位 Windows 上的 64 位 Outlook）上运行；如果没有先重新生成为 32 位应用程序，则 64 位 MAPI 应用程序不能在安装了 32 位 Outlook 和 32 位或 64 位 Windows 的计算机上运行。 图 1 所示为出现以上任意情况时显示的警报对话框。
  
**图 1. 用于大部分跨位数 MAPI 调用的错误消息。**

![用于大部分跨位数 MAPI 调用的错误消息](media/738905fb-57ae-4af7-b54b-a1676c80d3c3.JPG "用于大部分跨位数 MAPI 调用的错误消息")
  
但是，在 Windows-32-bit-on-Windows-64-bit (WOW64) 或 Windows-64-bit-on-Windows-32-bit (WOW32) 应用场景中，所有简单 MAPI 和 MAPI 元素中的一个函数调用 **MAPISendMail** 将会成功，不会产生以上警报。 此 WOW64 应用场景仅适用于 Windows 7。 

图 2 显示了 WOW64 应用场景，其中，32 位 MAPI 应用程序在已安装了 64 位 Windows 7 的计算机上调用 **MAPISendMail**。 在此应用场景中，MAPI 库将进行 COM 调用，以启动 64 位 Fixmapi 应用程序。 Fixmapi 应用程序将隐式链接至 MAPI 库，这会将函数调用路由至 Windows MAPI 存根，而后者反过来会将调用转发给 Outlook MAPI 存根，从而使 **MAPISendMail** 函数调用成功。 
  
**图 2. 在 WOW64 应用场景中处理 MAPISendMail。**

![在 WOW64 应用场景中处理 MAPISendMail](media/346ba974-4844-4b64-9dd1-d0f829ab99b3.gif "在 WOW64 应用场景中处理 MAPISendMail")
  
## <a name="see-also"></a>另请参阅

- [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)

