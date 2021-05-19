---
title: 开发提供程序的最佳做法
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 22e3de8a-c4f2-41a4-a5b1-c5b1bf06f724
description: 在 OSC 提供程序中开发 Outlook Social Connector 2013 (应遵循) 做法：
ms.openlocfilehash: 6a48a56d8065fb9a176ca6527340c99551cdb52a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425916"
---
# <a name="best-practices-for-developing-a-provider"></a>开发提供程序的最佳做法

在 OSC 提供程序中开发 Outlook Social Connector 2013 (应遵循) 做法：
  
- 出于安全考虑，通过 Internet 与服务器通信的提供程序应该将 HTTPS (超文本传输协议 (HTTP) 与安全套接字层 (SSL) ) 协议一同使用。 否则，在传输过程中可能会截获或公开电子邮件地址、社交网络活动和其他用户数据。
    
- 如果要为第三方社交网络开发 OSC 提供程序，提供商必须遵守社交网络的服务条款。
    
- 若要最大程度地减小提供程序下载包的大小，可以使用本机编译器（如 C++）或可以生成 COM 组件的其他工具生成提供程序。
    
- 在提供程序中，创建发送到社交网络的唯一用户代理，以跟踪提供商对社交网络的呼叫。
    
- [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)方法不应依赖通过 Internet 调用社交网络获取提供程序的功能。 例如，用户可以脱机启动Outlook;如果 OSC 调用 **GetCapabilities** 并且没有网络连接，**则 GetCapabilities** 调用不会返回 **有效的功能** XML。 最佳做法是，将 **功能** XML 存储为提供程序中的资源。 
    
- OSC 提供程序可以生成大量对社交网络的调用。 根据社交网络的服务条款，请考虑将好友缓存到 Outlook 文件夹，以减少从 OSC 到提供程序的呼叫数，进而减少从提供程序到社交网络的呼叫数。
    
- Office 2013 有 32 位和 64 位版本。 2010 Office 2010 Office版本仅在 32 位版本中可用。 64 位Office 2013 的默认安装Windows 32 位。 如果打算支持随 64 位 Office 2013 一起安装的 64 位版本的 OSC，还必须发布 64 位版本的提供程序。 
    
## <a name="see-also"></a>另请参阅

- [OSC 典型调用序列](osc-typical-calling-sequences.md)  
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)  
- [部署提供程序](deploying-a-provider.md)  
- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

