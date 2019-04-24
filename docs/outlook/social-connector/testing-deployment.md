---
title: 测试部署
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b585200-33e7-4607-a603-0c7e52a6b09d
description: 本主题介绍了有关安装和卸载 Outlook Social Connector (.osc) 提供程序时应测试的一些方案。
ms.openlocfilehash: 9c811683097a08b9f6e575d4ea2fee29cdd545d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329160"
---
# <a name="testing-deployment"></a>测试部署

本主题介绍了有关安装和卸载 Outlook Social Connector (.osc) 提供程序时应测试的一些方案。

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="presence-of-outlook-and-the-osc-on-client-computer"></a>客户端计算机上的 Outlook 和 .osc 的状态

因素安装 .osc 提供程序的影响包括操作系统的位数、outlook 的状态和位数以及在 outlook 中启用的 .osc。
  
可以为32位或64位的 .osc 版本编写一个 .osc 提供程序。 outlook 2010 和 outlook 2013 在32位和64位版本中均可用, office outlook 2003 和 office outlook 2007 仅在32位版本中可用。 在64位的 Windows 操作系统上, 您可以安装32位或64位的 Outlook。 在32位操作系统中, 只能安装32位, 但不能安装64位的 Outlook。 根据安装的 Outlook 版本和 .osc 提供程序本身的位数, 用户应使用适当的安装程序来安装适当位数的 .osc 提供程序。 例如, 如果安装了64位的 Outlook, 并且 .osc 提供程序是本机 COM 组件, 则32位 .osc 提供程序将不起作用, 并且用户必须使用适当的安装程序来安装64位的 .osc 提供程序。
  
您的 .osc 提供程序的部署代码可以假定用户在计算机上具有受支持的 Outlook 版本。 但是, 如果当前版本的 .osc 不在客户端计算机上, 则部署代码可以使用上的https://g.live.com特殊构造的 g 链接 url 下载并安装相应的 .osc 版本。 这些 g 链接取决于 Outlook 的版本和位数以及客户端计算机的区域设置。 有关使用 g-链接安装或更新 .osc 的详细信息, 请参阅[安装清单](installation-checklist.md)。
  
在安装 .osc 提供程序之前, outlook 用户应确保在 outlook 中启用了 .osc 加载项。
  
部署 .osc 提供程序的建议方法是使用 Windows Installer (.msi) 程序包。 测试以下每个方案以验证提供程序的部署的工作方式是否正确。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|outlook 不存在-outlook 2003 或 outlook 2007 未安装, outlook 2010 或 Microsoft Outlook 2013 尚未安装, 也未通过即点即用提供。  <br/> |部署失败。  <br/> |
|outlook 2003 或 outlook 2007 未安装, 但 outlook 2010 或 Microsoft Outlook 2013 已通过即点即用进行传递。  <br/> |部署了32位提供程序。  <br/> |
|已安装 outlook 2003 或 outlook 2007, 但未安装 .osc。  <br/> |安装程序将安装 .osc 和所有修补程序。 成功安装了 .osc 后, 安装程序将部署该提供程序。  <br/> |
|安装了 outlook 2003 或 outlook 2007, 并安装了早期版本的 .osc。  <br/> |安装程序通过 g-指向修补程序的链接更新了 .osc, 然后部署了该提供程序。  <br/> |
|安装了 Outlook 2003 或 2007, 并且 .osc 是最新的。  <br/> |安装程序将部署32位提供程序。  <br/> |
|已安装 Outlook 2010 或 Microsoft Outlook 2013, 但未安装 .osc。  <br/> |安装程序失败并出现相应的错误消息。  <br/> |
|安装了 Outlook 2010 或 Microsoft Outlook 2013, 并安装了旧版本的 .osc。  <br/> |适用于安装的 Outlook 2010 或 Microsoft Outlook 2013 的位数的安装程序, 通过 g-链接更新到修补程序的 .osc, 然后部署相应的提供程序。  <br/> |
|安装了 Outlook 2010 或 Microsoft Outlook 2013, 并且 .osc 是最新的。  <br/> |适用于安装的 Outlook 2010 或 Microsoft Outlook 2013 (32-bit 或 64) 的位数的安装程序将部署相应的提供程序。  <br/> |

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="installed-location-and-registry-keys"></a>安装的位置和注册表项

验证您的 .osc 提供商已部署的文件位置, 以及 Windows 注册表中创建提供程序的注册表项的位置。
  
### <a name="file-location-for-osc-provider-dlls"></a>.osc 提供程序 dll 的文件位置

对下表中列出的方案进行测试。 请注意, 该表列出了 .osc 提供程序 dll 的默认安装路径。 用户可以在安装这些 dll 的位置上进行自定义。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|Microsoft Outlook 2013 安装在客户端计算机上。  <br/> |提供程序 dll 部署到 Office15 文件夹中。 如果操作系统为64位, Microsoft Outlook 2013 为32位, 则将在 C:\Program Files (x86) \Microsoft 上部署32位 dll Office\Office15。 如果操作系统为64位, 而 Microsoft Outlook 2013 为64位, 则将在 C:\Program Files\Microsoft Office\Office15. 下部署64位 dll。 如果操作系统为32位, 将在 C:\Program Files\Microsoft Office\Office15. 下部署 dll  <br/> |
|在客户端计算机上安装了 Outlook 2010。  <br/> |提供程序 dll 部署到 Office14 文件夹中。 如果操作系统为64位, 而 Outlook 2010 为32位, 则将在 C:\Program Files (x86) \Microsoft 上部署32位 dll Office\Office14。 如果操作系统为64位, 而 Outlook 2010 为 64-位, 则将在 C:\Program Files\Microsoft Office\Office14. 下部署64位 dll。 如果操作系统为32位, 将在 C:\Program Files\Microsoft Office\Office14. 下部署 dll  <br/> |
|在客户端计算机上安装了 Outlook 2007。  <br/> |提供程序 dll 部署在 C:\Program Files\Microsoft Office\Office14. 下 安装 .osc 将创建 Office14 文件夹, 并且必须在任何提供程序 dll 之前安装 .osc。 请参阅上一节[状态: Outlook 和客户端计算机上的 .osc](#olosc_TestingDeployment_PresenceOfOutlook)。  <br/> |
|在客户端计算机上安装了 Outlook 2003。  <br/> |提供程序 dll 部署在 C:\Program Files\Microsoft Office\Office14. 下 安装 .osc 将创建 Office14 文件夹, 并且必须在任何提供程序 dll 之前安装 .osc。 请参阅上一节[状态: Outlook 和客户端计算机上的 .osc](#olosc_TestingDeployment_PresenceOfOutlook)。  <br/> |
|Microsoft Outlook 2013 未安装, 但在客户端计算机上通过即点即用进行传递。  <br/> |提供程序 dll 部署到 Office15 文件夹中。 如果操作系统为64位, 32-位 dll 在 C:\Program Files (x86) \Microsoft Office\Office15 或 C:\Program Files\Microsoft Office\Office15. 中部署 如果操作系统为32位, 将在 C:\Program Files\Microsoft Office\Office15. 下部署 dll 如果 Office15 文件夹不存在, 则安装将创建该文件夹。  <br/> |
|Outlook 2010 未安装, 但通过在客户端计算机上的即点即用进行传递。  <br/> |提供程序 dll 部署到 Office14 文件夹中。 如果操作系统为64位, 32-位 dll 在 C:\Program Files (x86) \Microsoft Office\Office14 或 C:\Program Files\Microsoft Office\Office14. 中部署 如果操作系统为32位, 将在 C:\Program Files\Microsoft Office\Office14. 下部署 dll 如果 Office14 文件夹不存在, 则安装将创建该文件夹。  <br/> |
   
### <a name="windows-registry-locations"></a>Windows 注册表位置

确认以下内容：
  
- .osc 提供程序安装程序在`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`或`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`中为 Windows 注册表中的 .osc 提供程序创建一个 ProgID 值。 
    
- 例外情况是, 如果客户端计算机在64位 Windows 操作系统上运行32位 Outlook。 在这种情况下, 可以`HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`在或`HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`中创建 ProgID。
    
- 注册表项应相同且位于同一位置, 如果相反, dll 由 regsvr32 注册。

<a name="olosc_TestingDeployment_PresenceOfOutlook"> </a>

## <a name="removing-the-installation"></a>删除安装

下面是一些测试, 用于验证卸载过程是否适用于您的 .osc 提供程序。
  
|**应用场景**|**预期行为**|
|:-----|:-----|
|用户选择卸载提供程序。  <br/> |提供程序卸载 dll 并清除注册表。  <br/> |
|用户选择取消提供程序的卸载过程。  <br/> |提供程序取消卸载过程, 并将用户恢复到卸载过程启动前的状态。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [注册提供程序](registering-a-provider.md)  
- [安装清单](installation-checklist.md)
- [准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)

