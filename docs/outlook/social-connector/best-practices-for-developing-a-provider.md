---
title: 开发提供程序的最佳做法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 22e3de8a-c4f2-41a4-a5b1-c5b1bf06f724
description: '在开发 Outlook Social Connector 2013 (.osc) 提供程序时, 应遵循以下做法:'
ms.openlocfilehash: 6a48a56d8065fb9a176ca6527340c99551cdb52a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281235"
---
# <a name="best-practices-for-developing-a-provider"></a>开发提供程序的最佳做法

在开发 Outlook Social Connector 2013 (.osc) 提供程序时, 应遵循以下做法:
  
- 出于安全考虑, 通过 Internet 与服务器通信的提供程序应使用 HTTPS (带有安全套接字层 (SSL) 协议的超文本传输协议 (HTTP)) 协议。 否则, 在传输过程中可能会发生电子邮件地址、社交网络活动以及其他用户数据可能会被截取或暴露的风险。
    
- 如果要为第三方社交网络开发一个 .osc 提供程序, 则提供商必须遵守社交网络的服务条款。
    
- 若要最大限度地减少提供程序下载包的大小, 请使用本机编译器 (如 c + +) 或任何其他可生成 COM 组件的工具生成提供程序。
    
- 在您的提供程序中, 创建一个发送到社交网络的唯一用户代理, 以跟踪提供商向社交网络发出的呼叫。
    
- [ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法不应依赖于在 Internet 上调用社交网络来获取提供程序的功能。 例如, 用户可以脱机启动 Outlook;如果 .osc 调用**GetCapabilities**且没有网络连接, 则**GetCapabilities**调用将不会返回有效的**功能**XML。 最佳做法是在提供程序中将**功能**XML 存储为资源。 
    
- 你的 .osc 提供商可以生成大量呼叫社交网络的呼叫。 根据你的社交网络的服务条款, 请考虑将好友缓存到 Outlook 文件夹, 以将来自 .osc 的呼叫数减少到提供商, 然后从你的提供商转到社交网络。
    
- Office 2013 在32位和64位版本中均可用。 office 2010 之前的 office 版本仅在32位版本中可用。 在64位 Windows 上安装的 Office 2013 的默认值为32位。 如果您打算支持与64位 Office 2013 一起安装的64位版本的 .osc, 则还必须发布提供程序的64位版本。 
    
## <a name="see-also"></a>另请参阅

- [.osc 典型调用序列](osc-typical-calling-sequences.md)  
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [部署提供程序](deploying-a-provider.md)  
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

