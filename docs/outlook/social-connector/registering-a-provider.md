---
title: 注册提供程序
manager: soliver
ms.date: 03/05/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b60b3634-4c8b-4273-97a0-0a8a5a8a5342
description: 本主题介绍在安装 Outlook Social Connector (.osc) 提供程序时使用的 Windows 注册表位置。
ms.openlocfilehash: a5f76850f9bebcba3c2bff31e799a3b012d6b91a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329209"
---
# <a name="registering-a-provider"></a>注册提供程序

本主题介绍在安装 Outlook Social Connector (.osc) 提供程序时使用的 Windows 注册表位置。
  
## <a name="com-registration"></a>COM 注册

您必须将 .osc 提供程序 DLL 配置为在安装过程中使用 COM 自注册或 regsvr32 进行注册。 提供程序 DLL 的 COM 注册在`HKEY_CLASSES_ROOT`注册表配置单元下注册 .osc 提供程序。 
  
在托管代码中开发的 .osc 提供程序具有 COM 可见的提供程序程序集。 应将单独的应用程序域用于提供程序组件。 否则, .osc 提供程序将使用其他组件使用的默认共享应用程序域, 并且提供程序可能无法按预期运行。
  
## <a name="registering-provider-progid"></a>注册提供程序 ProgID

每个 .osc 提供程序都必须注册一个`ProgID`编程标识符 ()。 提供程序安装程序可以选择以下位置之一来添加或删除`ProgID`:
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果仅为当前登录的用户安装了提供程序, 则提供程序安装程序应使用此位置。
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果为计算机上的所有用户安装了提供程序, 则提供程序安装程序应使用此位置。
    
.osc 在上述位置查找提供`ProgID`程序, 除非客户端计算机在64位 Windows 操作系统上运行32位 Outlook。 在这种情况下, 提供程序安装程序应选择`HKEY_CURRENT_USER`或`HKEY_LOCAL_MACHINE`配置单元中的以下位置之一: 
  
- `HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
对于即点即用版本的 Office, 提供程序安装程序应选择 HKEY_CURRENT_USER 或 HKEY_LOCAL_MACHINE 配置单元中的以下位置之一:
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Outlook\SocialConnector\SocialProviders`
    
## <a name="see-also"></a>另请参阅

- [安装清单](installation-checklist.md)
- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)

