---
title: 将 OSC 与 Outlook 和社交网络关联起来
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f33705cc-8add-42be-9d9f-f4e9245d83f5
description: outlook Social Connector (.osc) 可以显示在 Office 联系人卡片和 outlook 人员窗格活动、状态或与您相关联的任何人的照片更新中。
ms.openlocfilehash: 0ee9451e64f12e8ba371c1ba91a1379cff257313
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329253"
---
# <a name="relating-the-osc-with-outlook-and-social-networks"></a>将 OSC 与 Outlook 和社交网络关联起来

outlook Social Connector (.osc) 可以显示在 Office 联系人卡片和 outlook 人员窗格活动、状态或与您相关联的任何人的照片更新中。 默认情况下, .osc 显示从所选人员接收到的 Outlook 电子邮件、附件和会议请求。 如果所选人员和 Office 用户在 sharepoint 网站上进行协作, 则该 .osc 还会显示来自该 sharepoint 网站的文档更新和其他网站活动。 根据 office 用户感兴趣的关联上下文, Office 用户可以为业务线应用程序、内部企业网站或各种专业和社交网络网站 (如 LinkedIn) 安装 .osc 提供程序。Facebook 和 Windows Live。
  
为了支持在 office 客户端应用程序之间共享功能, .osc 核心引擎作为 Office 共享组件的一部分实现, 而 "人员" 窗格以 Outlook 外接程序的形式实现。 若要使用 .osc, Office 用户必须已在该客户端计算机上安装 outlook, 并将 outlook 配置为使用配置文件, 以便该 .osc 可以缓存联系人文件夹中的联系人。 
  
.osc 提供程序是一种组件对象模型 (COM) DLL, 它允许 .osc 以独立于每个社交网络的 api 的方式访问社交网络数据。 必须在客户端计算机上本地安装一个 .osc 提供程序 DLL。 社交网络的 .osc 提供程序通过 Internet 上的社交网络连接的 .osc (Outlook 的一部分)。
  
一个 .osc 提供程序必须实现一组接口 (定义为 .osc 提供程序可扩展性的一部分), 以便与 .osc 进行通信。 .osc 提供程序可扩展性可用作开放平台。
  
使用 .osc 的提供程序体系结构, 多个提供程序可以使用 .osc 核心引擎和聚合社会信息 (如好友和活动)。 图1说明了 .osc 提供程序的体系结构。
  
**图1。Outlook Social Connector 提供程序体系结构**

![社交网络、OSC 提供程序、OSC 和 Office](media/off15OSCRef_Architecture.gif)
  
## <a name="terminology"></a>术语

在此 Outlook Social Connector 提供程序参考中, 社交网络用于引用以下类型的网站: 
  
- 协作网站 (如 SharePoint)。
    
- 诸如 Facebook 和 Windows Live 等社交网络网站。
    
- 专业网络站点, 如 LinkedIn。
    
- 用于联网的其他业务线应用程序或公司内部网站。
    
"友元" 这一术语通常用于包括朋友、家人、同事、连接和任何其他 Office 用户在 SharePoint 等协作上下文中的关联, 或已添加到用户的社交网络帐户中。 非好友是朋友的活动更新中引用的人员, 但它们不是已添加到 Office 用户的社交网络帐户中的好友。 联系人是 Outlook 联系人文件夹中的人员。 
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

