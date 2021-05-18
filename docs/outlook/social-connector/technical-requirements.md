---
title: 技术要求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eff6d5d6-8855-4e54-a781-9deab8cc0aca
description: 本主题介绍支持的编程语言、COM 可见性和方法返回类型要求，以及 OSC Outlook (OSC) DLL 的详细信息。
ms.openlocfilehash: 14dfcf52d714177775c5610b5da91d174f81a132
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329153"
---
# <a name="technical-requirements"></a>技术要求

本主题介绍支持的编程语言、COM 可见性和方法返回类型要求，以及 OSC Outlook (OSC) DLL 的详细信息。 
  
## <a name="programming-language-and-com-requirements"></a>编程语言和 COM 要求

可以使用托管语言（如 Visual C# 或 Visual Basic）或非托管语言（如 Visual C++）创建 OSC 提供程序。 可以使用任何可以创建 COM 可见的 DLL 组件的工具来开发 OSC 提供程序。 决定使用托管语言还是非托管语言来开发提供程序时，应当考虑提供程序安装程序包的下载大小和依赖项。
  
OSC 提供程序必须是 COM 可见的，如以下内容所定义：
  
- 安装后，必须使用 COM 自注册或 regsvr32 注册 OSC 提供程序。
    
- OSC 提供程序 DLL 的 COM 注册在 HKCU 或 HKLM 下注册提供商。 
    
- 提供程序的 ProgID 注册在  `HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` 下。
    
- 使用托管语言开发的 OSC 提供程序是 COM 可见的。
    
- OSC 提供程序应向 Windows 注册表添加值，指示提供程序 DLL 支持单线程单元 (STA) 和多线程单元 (MTA) 模型。 有关 COM 线程模型详细信息，请参阅[OLE 线程模型的说明和工作。](https://support.microsoft.com/kb/150777)
    
OSC 提供程序扩展性中的方法必须返回基元类型，如 **字符串** 或 **布尔值**。 某些 **字符串** 返回值必须符合 OSC 提供程序扩展性架构定义。 仅支持 XML 作为返回值。 
  
## <a name="details-of-the-osc-provider-extensibility-dll"></a>OSC 提供程序扩展 DLL 的详细信息

支持 OSC 提供程序扩展性的组件是 OSC 提供程序扩展 DLL。 第三方开发人员可以使用这些扩展性接口生成 OSC 提供程序 DLL。 以下列表显示了 OSC 提供程序扩展 DLL 的详细信息：
  
- 扩展性 DLL 文件名：socialprovider.dll
    
- 扩展性 DLL 友好名称：Microsoft Outlook社交提供程序扩展性
    
- 扩展性 DLL 主要版本：15.0
    
- Extensibiilty DLL TypeLib 版本：1.1
    
## <a name="miscellaneous-technical-information"></a>杂项技术信息

OSC 提供程序扩展 (不支持 JavaScript (JSON) JSON 对象表示法。
  
XML 分析程序上没有任何依赖关系。 OSC 提供程序可以使用 Office 中包含的 XML 分析程序（如 Microsoft XML Core Services (MSXML)  (MSXML) ）、使用 Microsoft .NET Framework 中内置的 XML 分析功能或使用第三方 XML 分析程序。 
  
## <a name="see-also"></a>另请参阅

- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)  
- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)  
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

