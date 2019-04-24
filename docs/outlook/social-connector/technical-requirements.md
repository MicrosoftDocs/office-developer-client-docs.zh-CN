---
title: 技术要求
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: eff6d5d6-8855-4e54-a781-9deab8cc0aca
description: 本主题介绍了受支持的编程语言、COM 可见性和方法返回类型要求, 以及 Outlook Social Connector (.osc) 提供程序扩展 DLL 的详细信息。
ms.openlocfilehash: 14dfcf52d714177775c5610b5da91d174f81a132
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329153"
---
# <a name="technical-requirements"></a>技术要求

本主题介绍了受支持的编程语言、COM 可见性和方法返回类型要求, 以及 Outlook Social Connector (.osc) 提供程序扩展 DLL 的详细信息。 
  
## <a name="programming-language-and-com-requirements"></a>编程语言和 COM 要求

可以使用托管语言 (如 visual c # 或 visual Basic) 或非托管语言 (如 visual c + +) 创建 .osc 提供程序。 您可以使用任何可创建 COM 可见的 DLL 组件来开发 .osc 提供程序的工具。 使用托管或非托管语言开发提供程序的决定应考虑提供程序安装包的下载大小和依赖项。
  
.osc 提供程序必须按以下方式定义的 COM 可见:
  
- 安装完成后, 必须使用 COM 自注册或 regsvr32 注册一个 .osc 提供程序。
    
- 您的 .osc 提供程序 DLL 的 COM 注册会在 HKCU 或 HKLM 下注册提供程序。 
    
- 提供程序的 ProgID 在`HKCU\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`中注册。
    
- 在托管语言中开发的一个 .osc 提供程序是 COM 可见的。
    
- .osc 提供程序应将值添加到 Windows 注册表中, 以指示提供程序 DLL 支持单线程单元 (STA) 和多线程单元 (MTA) 线程模型。 有关 COM 线程模型的详细信息, 请参阅[OLE 线程模型的说明和工作原理](https://support.microsoft.com/kb/150777)。
    
.osc 提供程序扩展性中的方法必须返回基元类型, 如**string**或**bool**。 某些**字符串**返回值必须符合 .osc 提供程序可扩展性的架构定义。 仅支持 XML 作为返回值。 
  
## <a name="details-of-the-osc-provider-extensibility-dll"></a>.osc 提供程序扩展性 DLL 的详细信息

支持 .osc 提供程序可扩展性的组件是 .osc 提供程序扩展性 DLL。 第三方开发人员可以使用这些扩展性接口生成 .osc 提供程序 dll。 以下列表显示了 .osc 提供程序扩展性 DLL 的详细信息:
  
- 可扩展性 DLL 文件名: socialprovider
    
- 可扩展性 DLL 友好名称: Microsoft Outlook Social Provider 扩展性
    
- 可扩展性 DLL 主要版本: 15。0
    
- Extensibiilty DLL TypeLib 版本: 1。1
    
## <a name="miscellaneous-technical-information"></a>其他技术信息

在 .osc 提供程序扩展性模型中不支持 JavaScript 对象表示法 (JSON)。
  
XML 分析程序没有任何依赖项。 .osc 提供程序可以使用 Office 附带的 xml 分析程序 (如 microsoft XML Core Services (MSXML)), 使用 microsoft .net Framework 中内置的 xml 分析功能, 或使用第三方 xml 分析器。 
  
## <a name="see-also"></a>另请参阅

- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)  
- [学习开发提供程序的快速步骤](quick-steps-for-learning-to-develop-a-provider.md)
- [部署提供程序](deploying-a-provider.md)  
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

