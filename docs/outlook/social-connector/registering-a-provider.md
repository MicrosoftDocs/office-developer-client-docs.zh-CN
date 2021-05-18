---
title: 注册提供程序
manager: soliver
ms.date: 03/05/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b60b3634-4c8b-4273-97a0-0a8a5a8a5342
description: 本主题介绍Windows OSC) 提供程序安装 Outlook Social Connector 时所使用的 (位置。
ms.openlocfilehash: a5f76850f9bebcba3c2bff31e799a3b012d6b91a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421758"
---
# <a name="registering-a-provider"></a>注册提供程序

本主题介绍Windows OSC) 提供程序安装 Outlook Social Connector 时所使用的 (位置。
  
## <a name="com-registration"></a>COM 注册

您必须配置 OSC 提供程序 DLL 以在安装过程中使用 COM 自注册或 regsvr32 进行注册。 提供程序 DLL 的 COM 注册将 OSC 提供程序注册到 `HKEY_CLASSES_ROOT` 注册表配置单元下。 
  
在托管代码中开发的 OSC 提供程序具有 COM 可见的提供程序程序集。 您应该对提供程序组件使用单独的应用程序域。 否则，OSC 提供程序将使用其他组件使用的默认共享应用程序域，并且该提供程序可能无法按预期运行。
  
## <a name="registering-provider-progid"></a>注册提供程序 ProgID

每个 OSC 提供程序必须注册一个编程标识符 `ProgID` () 。 提供程序安装程序可以选择以下位置之一来添加或删除 `ProgID` ：
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果仅为当前登录的用户安装了提供程序，则提供程序安装程序应使用此位置。
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果为计算机上所有用户安装提供程序，则提供程序安装程序应使用此位置。
    
除非客户端计算机在 64 位操作系统上运行 32 位 Outlook，否则 OSC 将查找Windows `ProgID` 提供程序。 在这种情况下，提供程序安装程序应在 或 配置单元中选择以下位置  `HKEY_CURRENT_USER` 之  `HKEY_LOCAL_MACHINE` 一： 
  
- `HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
对于该版本的 Office，提供程序安装程序应在 HKEY_CURRENT_USER 或 HKEY_LOCAL_MACHINE 配置单元中选择以下位置之一：
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Outlook\SocialConnector\SocialProviders`
    
## <a name="see-also"></a>另请参阅

- [安装清单](installation-checklist.md)
- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)

