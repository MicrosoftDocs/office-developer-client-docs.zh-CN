---
title: 测试部署
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b585200-33e7-4607-a603-0c7e52a6b09d
description: 本主题介绍一些应测试的用于安装和卸载 OSC (Outlook Social Connector) 方案。
ms.openlocfilehash: 9c811683097a08b9f6e575d4ea2fee29cdd545d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329160"
---
# <a name="testing-deployment"></a>测试部署

本主题介绍一些应测试的用于安装和卸载 OSC (Outlook Social Connector) 方案。

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="presence-of-outlook-and-the-osc-on-client-computer"></a>客户端计算机上存在 Outlook 和 OSC

影响安装 OSC 提供程序的因素包括操作系统的位、Outlook 的存在和位以及 Outlook 中启用的 OSC。
  
可以针对 32 位或 64 位版本的 OSC 编写 OSC 提供程序。 Outlook 2010 和 Outlook 2013 同时提供 32 位和 64 位版本，Office Outlook 2003 和 Office Outlook 2007 仅提供 32 位版本。 在 64 位 Windows 操作系统上，可以安装 32 位或 64 位 Outlook。 在 32 位操作系统上，只能安装 32 位，但不能安装 64 位 Outlook。 根据已安装版本的 Outlook 和 OSC 提供程序本身的位度，用户应该使用相应的安装程序来安装适当位位的 OSC 提供程序。 例如，如果安装了 64 位 Outlook，并且 OSC 提供程序是本机 COM 组件，则 32 位 OSC 提供程序将不起作用，并且用户必须使用相应的安装程序来安装 64 位 OSC 提供程序。
  
OSC 提供程序的部署代码可以假定用户在计算机上具有受支持的 Outlook 版本。 但是，如果当前版本的 OSC 不在客户端计算机上，则部署代码可以在 上使用专门构建的 g-link URL 下载并安装相应的 OSC 版本 https://g.live.com 。 这些 g 链接取决于 Outlook 的版本和位以及客户端计算机区域设置。 有关使用 g 链接安装或更新 OSC 的信息，请参阅安装 [清单](installation-checklist.md)。
  
在安装 OSC 提供程序之前，Outlook 用户应确保在 Outlook 中启用了 OSC 外接程序。
  
部署 OSC 提供程序的建议方法是使用 Windows Installer (.msi) 程序包。 测试以下每个方案，验证部署是否适合提供程序。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|Outlook 不存在 - 未安装 Outlook 2003 或 Outlook 2007，并且未安装 Outlook 2010 或 Microsoft Outlook 2013，也未通过即点即用交付。  <br/> |部署失败。  <br/> |
|Outlook 2003 或 Outlook 2007 未安装，但 Outlook 2010 或 Microsoft Outlook 2013 已由即点即用提供。  <br/> |部署了 32 位提供程序。  <br/> |
|已安装 Outlook 2003 或 Outlook 2007，但不安装 OSC。  <br/> |安装程序将安装 OSC 以及所有修补程序。 成功安装 OSC 后，安装程序将部署提供程序。  <br/> |
|安装了 Outlook 2003 或 Outlook 2007，并安装了 OSC 的早期版本。  <br/> |安装程序通过指向修补程序的 g 链接更新 OSC，然后部署提供商。  <br/> |
|安装了 Outlook 2003 或 2007，并且 OSC 是最新的。  <br/> |安装程序部署 32 位提供程序。  <br/> |
|已安装 Outlook 2010 或 Microsoft Outlook 2013，但不安装 OSC。  <br/> |安装程序失败，并出现相应的错误消息。  <br/> |
|安装了 Outlook 2010 或 Microsoft Outlook 2013，并安装了较旧版本的 OSC。  <br/> |适用于已安装的 Outlook 2010 或 Microsoft Outlook 2013 的位的安装程序，通过指向修补程序的 g 链接更新 OSC，然后部署相应的提供程序。  <br/> |
|安装了 Outlook 2010 或 Microsoft Outlook 2013，并且 OSC 是最新的。  <br/> |适用于已安装的 Outlook 2010 或 Microsoft Outlook 2013 (32 位或 64 位) 的安装程序将部署相应的提供程序。  <br/> |

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="installed-location-and-registry-keys"></a>安装的位置和注册表项

验证已部署 OSC 提供程序的文件位置，以及创建提供程序注册表项的 Windows 注册表中的位置。
  
### <a name="file-location-for-osc-provider-dlls"></a>OSC 提供程序 DLL 的文件位置

测试下表中列出的方案。 请注意，该表列出了 OSC 提供程序 DLL 的默认安装路径。 用户可以自定义安装这些 DLL 的地方。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|Microsoft Outlook 2013 安装在客户端计算机上。  <br/> |提供程序 DLL 将部署到 Office15 文件夹中。 如果操作系统为 64 位且 Microsoft Outlook 2013 为 32 位，则 32 位 DLL 部署在 C：\Program Files (x86) \Microsoft Office\Office15 下。 如果操作系统为 64 位且 Microsoft Outlook 2013 为 64 位，则 64 位 DLL 部署在 C：\Program Files\Microsoft Office\Office15 下。 如果操作系统为 32 位，DLL 将部署在 C：\Program Files\Microsoft Office\Office15 下。  <br/> |
|Outlook 2010 安装在客户端计算机上。  <br/> |提供程序 DLL 将部署到 Office14 文件夹中。 如果操作系统为 64 位且 Outlook 2010 为 32 位，则 32 位 DLL 部署在 C：\Program Files (x86) \Microsoft Office\Office14 下。 如果操作系统为 64 位，Outlook 2010 为 64 位，则 64 位 DLL 部署在 C：\Program Files\Microsoft Office\Office14 下。 如果操作系统为 32 位，DLL 将部署在 C：\Program Files\Microsoft Office\Office14 下。  <br/> |
|Outlook 2007 安装在客户端计算机上。  <br/> |提供程序 DLL 部署在 C：\Program Files\Microsoft Office\Office14 下。 安装 OSC 将创建 Office14 文件夹，并且 OSC 应在任何提供程序 DLL 之前安装。 请参阅上一部分客户端计算机上的 Outlook 和 [OSC 状态](#olosc_TestingDeployment_PresenceOfOutlook)。  <br/> |
|Outlook 2003 安装在客户端计算机上。  <br/> |提供程序 DLL 部署在 C：\Program Files\Microsoft Office\Office14 下。 安装 OSC 将创建 Office14 文件夹，并且 OSC 应在任何提供程序 DLL 之前安装。 请参阅上一部分客户端计算机上的 Outlook 和 [OSC 状态](#olosc_TestingDeployment_PresenceOfOutlook)。  <br/> |
|Microsoft Outlook 2013 未安装，而是通过即点即用在客户端计算机上交付。  <br/> |提供程序 DLL 将部署到 Office15 文件夹中。 如果操作系统为 64 位，则 32 位 DLL 部署在 C：\Program Files (x86) \Microsoft Office\Office15 或 C：\Program Files\Microsoft Office\Office15 下。 如果操作系统为 32 位，DLL 将部署在 C：\Program Files\Microsoft Office\Office15 下。 如果 Office15 文件夹不存在，则安装会创建该文件夹。  <br/> |
|Outlook 2010 未安装，而是通过即点即用在客户端计算机上交付。  <br/> |提供程序 DLL 将部署到 Office14 文件夹中。 如果操作系统为 64 位，则 32 位 DLL 部署在 C：\Program Files (x86) \Microsoft Office\Office14 或 C：\Program Files\Microsoft Office\Office14 下。 如果操作系统为 32 位，DLL 将部署在 C：\Program Files\Microsoft Office\Office14 下。 如果 Office14 文件夹不存在，则安装会创建该文件夹。  <br/> |
   
### <a name="windows-registry-locations"></a>Windows 注册表位置

确认以下内容：
  
- OSC 提供程序安装程序在 或 的 Windows 注册表中为 OSC 提供程序创建 ProgID  `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` 值  `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` 。 
    
- 例外情况是客户端计算机在 64 位 Windows 操作系统上运行 32 位 Outlook。 在这种情况下，在 或 中创建 ProgID。 `HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders` `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- 如果 DLL 是由用户注册的，则注册表项应该相同且位于regsvr32.exe。

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="removing-the-installation"></a>删除安装

下面是一些测试，用于验证卸载过程是否适用于您的 OSC 提供程序。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|用户选择卸载提供程序。  <br/> |提供程序卸载 DLL 并清除注册表。  <br/> |
|用户选择取消提供程序的卸载过程。  <br/> |提供程序取消卸载过程，并让用户在卸载过程启动之前恢复状态。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [注册提供程序](registering-a-provider.md)  
- [安装清单](installation-checklist.md)
- [准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)

