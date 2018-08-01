---
title: 开发提供程序的最佳做法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 22e3de8a-c4f2-41a4-a5b1-c5b1bf06f724
description: 开发 Outlook Social Connector 2013 (OSC) 提供程序时应遵循以下做法：
ms.openlocfilehash: a6ee9d54f33bbc855d178aba844a8f65ec92f964
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779196"
---
# <a name="best-practices-for-developing-a-provider"></a>开发提供程序的最佳做法

开发 Outlook Social Connector 2013 (OSC) 提供程序时应遵循以下做法：
  
- 出于安全考虑，通过 Internet 与服务器进行通信的提供程序应使用 HTTPS (超文本传输协议 (HTTP) 使用安全套接字层 (SSL)) 协议。 否则，将风险的电子邮件地址、 社交网络活动和其他用户无法截获或在传输过程中公开数据。
    
- 如果要开发 OSC 提供程序的第三方社交网络，您的提供商必须符合到社交网络的术语的服务。
    
- 大程度地减少提供下载程序包的大小，请使用如 c + + 或任何其他可构建 COM 组件的工具本机编译器生成提供程序。
    
- 提供程序，创建唯一的用户代理发送到社交网络跟踪对到社交网络提供程序发出的呼叫。
    
- [ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法不应依赖于通过 Internet 获取的功能提供程序的调用社交网络。 例如，用户可以开始 Outlook 脱机;如果没有网络连接 OSC 调用**GetCapabilities** ， **GetCapabilities**呼叫不会返回有效**功能**XML。 最佳做法是为您提供程序中的资源存储**功能**XML。 
    
- OSC 提供程序可以生成大量到社交网络的呼叫。 这取决于您的社交网络服务条款，请考虑缓存到 Outlook 文件夹朋友以减少的呼叫数从到您的提供商 OSC 和，依次到社交网络提供商。
    
- Office 2013 是 32 位和 64 位版本中提供。 Office 2010 之前版本的是 office 的仅在 32 位版本中可用。 Office 2013 64 位 Windows 上的默认安装 32 位。 如果您想要支持 OSC 随 64 位 Office 2013 安装的 64 位版本，您还必须释放您的提供商的 64 位版本。 
    
## <a name="see-also"></a>另请参阅

- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)  
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [部署提供程序](deploying-a-provider.md)  
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

