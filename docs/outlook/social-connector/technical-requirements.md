---
title: 技术要求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eff6d5d6-8855-4e54-a781-9deab8cc0aca
description: 本主题介绍支持的编程语言，COM 可见性和方法可返回类型要求和 Outlook Social Connector (OSC) 提供程序扩展性 DLL 的详细信息。
ms.openlocfilehash: 14dfcf52d714177775c5610b5da91d174f81a132
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383112"
---
# <a name="technical-requirements"></a>技术要求

本主题介绍支持的编程语言，COM 可见性和方法可返回类型要求和 Outlook Social Connector (OSC) 提供程序扩展性 DLL 的详细信息。 
  
## <a name="programming-language-and-com-requirements"></a>编程语言和 COM 要求

您可以通过使用 Visual C# 或 Visual Basic 中，如托管的语言或非托管如 Visual c + + 语言创建 OSC 提供程序。 您可以使用任何工具，可以创建一个 COM 可见 DLL 组件来开发 OSC 提供程序。 使用托管或非托管语言，以开发提供程序的决策应考虑到帐户下载大小和提供程序安装程序包的依赖项。
  
OSC 提供程序必须是 COM 可见，由以下定义：
  
- 安装完成后，必须通过使用 COM 注册或 regsvr32 注册 OSC 提供程序。
    
- OSC 提供程序 DLL 的 COM 注册注册 HKCU 或 HKLM 下的提供程序。 
    
- 提供程序的 ProgID 注册下`HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`。
    
- OSC 提供程序托管的语言开发是 COM 可见。
    
- OSC 提供程序应将值添加到 Windows 注册表的指示提供程序 DLL 支持单线程单元 (STA) 和多线程的单元 (MTA) 线程模型。 有关 COM 线程模型的详细信息，请参阅[说明和工作原理的 OLE 线程模型](https://support.microsoft.com/kb/150777)。
    
OSC 提供程序扩展性中的方法必须返回如**字符串**或**bool**基元类型。 某些**字符串**返回的值必须遵守 OSC 提供程序扩展性的架构定义。 仅 XML 的返回值为支持。 
  
## <a name="details-of-the-osc-provider-extensibility-dll"></a>OSC 提供程序扩展性 DLL 的详细信息

支持 OSC 提供程序扩展性的组件是 OSC 提供程序扩展性 DLL。 第三方开发人员可以通过使用这些扩展性接口构建 OSC 提供程序 Dll。 以下列表显示了 OSC 提供程序扩展性 DLL 的详细信息：
  
- 扩展性 DLL 文件名称： socialprovider.dll
    
- 扩展性 DLL 友好名称： Microsoft Outlook 社交提供程序扩展性
    
- 扩展性 DLL 主要版本： 15.0
    
- Extensibiilty DLL 类型库的版本： 1.1
    
## <a name="miscellaneous-technical-information"></a>Miscellaneous 的技术信息

OSC 提供程序扩展性模型中不支持 JavaScript 对象表示法 (JSON)。
  
XML 分析中没有任何关系。 OSC 提供程序可以使用 XML 分析程序随 Office，如 Microsoft XML Core Services (MSXML)、 使用 XML 分析功能构建到 Microsoft.NET Framework，或使用第三方 XML 分析程序。 
  
## <a name="see-also"></a>另请参阅

- [开发提供程序的最佳做法](best-practices-for-developing-a-provider.md)  
- [快速学习开发提供程序的步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)  
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

