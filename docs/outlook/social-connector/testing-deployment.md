---
title: 测试部署
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b585200-33e7-4607-a603-0c7e52a6b09d
description: 本主题介绍一些您应测试关于安装和卸载 Outlook Social Connector (OSC) 提供程序的方案。
ms.openlocfilehash: 9c811683097a08b9f6e575d4ea2fee29cdd545d6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383931"
---
# <a name="testing-deployment"></a>测试部署

本主题介绍一些您应测试关于安装和卸载 Outlook Social Connector (OSC) 提供程序的方案。

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="presence-of-outlook-and-the-osc-on-client-computer"></a>Outlook 和客户端计算机上的 OSC 的状态

因素影响安装 OSC 提供程序包括操作系统、 状态和位数的 Outlook，在 Outlook 中启用 OSC 的位数。
  
OSC 提供程序可以编写任一 OSC 32 位或 64 位版本。 Outlook 2010 和 Outlook 2013 32 位和 64 位版本中可用，并且 Office Outlook 2003 和 Office Outlook 2007 均在仅 32 位版本中可用。 在 64 位 Windows 操作系统中，您可以安装 32 位或 64 位 Outlook。 32 位操作系统上您可以安装仅 32 位，但不是 64 位 Outlook。 根据安装的 Outlook 和 OSC 提供程序本身版本的位数，用户应使用适当的安装程序来安装 OSC 提供程序的相应位数。 例如，如果安装了 64 位 Outlook，并且 OSC 提供程序是一个本机 COM 组件，32 位 OSC 提供程序将不起作用，用户必须使用适当的安装程序来安装 64 位 OSC 提供程序。
  
OSC 提供程序的部署代码可以假定用户具有受支持的计算机上的 Outlook 版本。 但是，如果当前版本的 OSC 不在客户端计算机上，您部署的代码可以下载和安装 OSC 的适当版本上使用特殊构建的 g 链接 Url https://g.live.com。 这些 g 链接取决于的版本和 Outlook 的位数和客户端计算机的区域设置。 有关使用 g 链接安装或更新 OSC 的详细信息，请参阅[安装清单](installation-checklist.md)。
  
在安装之前 OSC 提供程序，Outlook 用户应确保 OSC 外接程序启用 Outlook 中。
  
部署 OSC 提供程序的建议的方法是使用 Windows Installer (.msi) 程序包。 测试以下每个方案提供程序中适当地验证部署的工作方式。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|Outlook 不存在-未安装 Outlook 2003 或 Outlook 2007，并不安装 Outlook 2010 或 Microsoft Outlook 2013 也已它传递通过单击即点即用。  <br/> |部署将失败。  <br/> |
|未安装 outlook 2003 或 Outlook 2007，但 Outlook 2010 或 Microsoft Outlook 2013 已被送达通过单击即点即用。  <br/> |部署的 32 位提供程序。  <br/> |
|安装了 outlook 2003 或 Outlook 2007，但未安装 OSC。  <br/> |安装程序安装 OSC 和所有修补程序。 一旦 OSC 已成功安装，安装程序将部署提供程序。  <br/> |
|安装 outlook 2003 或 Outlook 2007，并安装早期版本的 OSC。  <br/> |安装程序更新 OSC，通过修补程序，到 g 链接，然后再部署提供程序。  <br/> |
|安装 outlook 2003 或 2007年和 OSC 是最新。  <br/> |安装程序部署的 32 位提供程序。  <br/> |
|Outlook 2010 或 Microsoft Outlook 2013 已安装但未安装 OSC。  <br/> |安装程序将失败并相应的错误消息。  <br/> |
|Outlook 2010 或 Microsoft Outlook 2013 安装和安装 OSC 较旧版本。  <br/> |安装程序适合于已安装的 Outlook 2010 或 Microsoft Outlook 2013 的位数更新修补程序、 OSC 通过 g 链接，然后再部署相应的提供程序。  <br/> |
|Outlook 2010 或 Microsoft Outlook 2013 安装和 OSC 是最新。  <br/> |适用于已安装的 Outlook 2010 或 Microsoft Outlook 2013 （32 位或 64 位） 的位数，安装程序部署相应的提供程序。  <br/> |

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="installed-location-and-registry-keys"></a>安装的位置和注册表项

验证文件位置其中已经部署了您 OSC 提供程序，以及在其中创建提供程序的注册表项的 Windows 注册表中的位置。
  
### <a name="file-location-for-osc-provider-dlls"></a>OSC 提供程序 Dll 的文件位置

下表中所列，则测试方案。 记下表列出了默认安装路径为 OSC 提供程序 Dll。 用户可以自定义这些 Dll 的安装位置。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|客户端计算机上安装 Microsoft Outlook 2013。  <br/> |提供程序 Dll 部署到 Office15 文件夹。 如果 Microsoft Outlook 2013 是 32 位操作系统是 64 位，32 位 Dll 下为 C:\Program Files (x86) \Microsoft Office\Office15 部署。 如果 Microsoft Outlook 2013 是 64 位操作系统是 64 位，C:\Program Files\Microsoft Office\Office15 下部署 64 位 Dll。 如果操作系统，32 位下 C:\Program Files\Microsoft Office\Office15 部署 Dll。  <br/> |
|客户端计算机上安装 outlook 2010。  <br/> |提供程序 Dll 部署到 Office14 文件夹。 如果 Outlook 2010 是 32 位操作系统是 64 位，32 位 Dll 下为 C:\Program Files (x86) \Microsoft Office\Office14 部署。 如果 Outlook 2010 中为 64 位操作系统是 64 位，在 C:\Program Files\Microsoft Office\Office14 下部署 64 位 Dll。 如果操作系统，32 位 Dll 部署在 C:\Program Files\Microsoft Office\Office14 下。  <br/> |
|客户端计算机上安装 outlook 2007。  <br/> |在 C:\Program Files\Microsoft Office\Office14 下部署提供程序 Dll。 安装 OSC 创建 Office14 文件夹中，并应在任何提供程序 Dll 之前安装 OSC。 请参阅上一节[状态的 Outlook 和客户端计算机上的 OSC](#olosc_TestingDeployment_PresenceOfOutlook)。  <br/> |
|客户端计算机上安装 outlook 2003。  <br/> |在 C:\Program Files\Microsoft Office\Office14 下部署提供程序 Dll。 安装 OSC 创建 Office14 文件夹中，并应在任何提供程序 Dll 之前安装 OSC。 请参阅上一节[状态的 Outlook 和客户端计算机上的 OSC](#olosc_TestingDeployment_PresenceOfOutlook)。  <br/> |
|不安装但未由单击即点即用分发客户端计算机上 Microsoft Outlook 2013。  <br/> |提供程序 Dll 部署到 Office15 文件夹。 64 位，32 位操作系统是否为 C:\Program Files (x86) \Microsoft Office\Office15 或 C:\Program Files\Microsoft Office\Office15 下部署 Dll。 如果操作系统，32 位下 C:\Program Files\Microsoft Office\Office15 部署 Dll。 如果 Office15 文件夹不存在，则安装创建文件夹。  <br/> |
|Outlook 2010 中不是安装而由单击即点即用分发客户端计算机上。  <br/> |提供程序 Dll 部署到 Office14 文件夹。 64 位，32 位操作系统是否为 C:\Program Files (x86) \Microsoft Office\Office14 或 C:\Program Files\Microsoft Office\Office14 下部署 Dll。 如果操作系统，32 位 Dll 部署在 C:\Program Files\Microsoft Office\Office14 下。 如果 Office14 文件夹不存在，则安装创建文件夹。  <br/> |
   
### <a name="windows-registry-locations"></a>Windows 注册表位置

确认以下各项：
  
- OSC 提供程序安装程序在 Windows 注册表中 OSC 提供程序创建一个 ProgID 值`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`或`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`。 
    
- 例外情况是客户端计算机具有 32 位 Outlook 在 64 位 Windows 操作系统上运行。 在这种情况下，在创建 ProgID`HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`或`HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`。
    
- 注册表项应相同和如果，而是由 regsvr32.exe 注册 Dll 为相同位置中。

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="removing-the-installation"></a>删除安装

以下是一些测试，以确认卸载过程正常 OSC 提供程序。
  
|**应用场景**|**预期的行为**|
|:-----|:-----|
|用户选择卸载提供程序。  <br/> |提供程序卸载 Dll，并清除注册表。  <br/> |
|用户选择取消提供程序的卸载过程。  <br/> |提供程序取消卸载过程，并将用户返回到卸载过程开始之前的状态。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [注册提供程序](registering-a-provider.md)  
- [安装清单](installation-checklist.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

