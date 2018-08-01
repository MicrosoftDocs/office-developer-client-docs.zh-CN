---
title: 注册提供程序
manager: soliver
ms.date: 03/05/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b60b3634-4c8b-4273-97a0-0a8a5a8a5342
description: 本主题介绍安装 Outlook Social Connector (OSC) 提供程序时所使用的 Windows 注册表位置。
ms.openlocfilehash: 3ec594ec94b045d2ceb583144781a5746b945b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779321"
---
# <a name="registering-a-provider"></a>注册提供程序

本主题介绍安装 Outlook Social Connector (OSC) 提供程序时所使用的 Windows 注册表位置。
  
## <a name="com-registration"></a>COM 注册

您必须配置 OSC 提供程序注册安装过程中使用 COM 注册或 regsvr32 的 DLL。 COM 注册提供程序 DLL 的注册下的 OSC 提供程序`HKEY_CLASSES_ROOT`注册表配置单元。 
  
在托管代码开发 OSC 提供程序具有 COM 可见的提供程序程序集。 提供程序组件，您应使用单独的应用程序域。 否则为 OSC 提供程序使用的默认共享应用程序域由其他组件，并提供程序可能不会按预期。
  
## <a name="registering-provider-progid"></a>注册提供程序 ProgID

每个 OSC 提供程序必须注册的编程标识符 (`ProgID`)。 提供程序安装程序可以选择要添加或删除的以下位置之一`ProgID`:
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果提供程序安装仅为当前登录的用户提供程序安装程序应使用此位置。
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果提供程序为所有用户的计算机上安装的提供程序安装程序应使用此位置。
    
OSC 提供程序查找`ProgID`在上面的位置，除非客户端计算机具有 32 位 Outlook 在 64 位 Windows 操作系统上运行。 在这种情况下，提供程序安装程序应选择中的以下位置之一`HKEY_CURRENT_USER`或`HKEY_LOCAL_MACHINE`配置单元： 
  
- `HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
单击即点即用版本的 Office，提供程序安装程序应选择在以下位置之一在 HKEY_CURRENT_USER 或 HKEY_LOCAL_MACHINE 配置单元：
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Outlook\SocialConnector\SocialProviders`
    
## <a name="see-also"></a>另请参阅

- [安装清单](installation-checklist.md)
- [快速学习开发提供程序的步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)

