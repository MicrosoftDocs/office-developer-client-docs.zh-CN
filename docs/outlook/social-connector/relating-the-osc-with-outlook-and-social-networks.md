---
title: 将 OSC 与 Outlook 和社交网络关联起来
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f33705cc-8add-42be-9d9f-f4e9245d83f5
description: the Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities， status， or photo updates for a coworker， friend， or any person you are associated with.
ms.openlocfilehash: 0ee9451e64f12e8ba371c1ba91a1379cff257313
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428009"
---
# <a name="relating-the-osc-with-outlook-and-social-networks"></a>将 OSC 与 Outlook 和社交网络关联起来

the Outlook Social Connector (OSC) can display in the Office Contact Card and Outlook People Pane activities， status， or photo updates for a coworker， friend， or any person you are associated with. 默认情况下，OSC 显示Outlook用户收到的电子邮件、附件和会议请求的信息。 如果所选用户和Office在网站中SharePoint协作，OSC 还将显示来自该站点的文档更新SharePoint活动。 根据 Office 用户感兴趣的关联上下文，Office 用户可以为业务线应用程序、内部公司网站或各种专业和社交网络网站（如 LinkedIn、Facebook 和 Windows Live）安装 OSC 提供程序。
  
为了支持跨 Office 客户端应用程序共享功能，OSC 核心引擎作为 Office 共享组件的一部分实现，并且人员窗格作为 Outlook 外接程序实现。 若要使用 OSC，Office用户必须在该客户端计算机上安装 Outlook 并使用配置文件配置 Outlook，以便 OSC 可以将联系人缓存到"联系人"文件夹中。 
  
OSC 提供程序是组件对象模型 (COM) DLL，它允许 OSC 以独立于每个社交网络的 API 的方式访问社交网络数据。 必须在客户端计算机上本地安装 OSC 提供程序 DLL。 社交网络的 OSC 提供程序将 OSC（作为 Outlook的一部分）与 Internet 上的社交网络连接。
  
OSC 提供程序必须实现一组接口（定义为 OSC 提供程序扩展的一部分）以与 OSC 通信。 OSC 提供程序扩展性作为开放平台提供。
  
OSC 的提供程序体系结构允许多个提供程序使用 OSC 核心引擎并聚合好友和活动等社交信息。 图 1 说明了 OSC 提供程序体系结构。
  
**图 1.OutlookSocial Connector 提供程序体系结构**

![社交网络、OSC 提供程序、OSC 和 Office](media/off15OSCRef_Architecture.gif)
  
## <a name="terminology"></a>术语

在此Outlook连接器提供程序参考"中，社交网络用于引用以下类型的网站： 
  
- 协作网站，如SharePoint。
    
- 社交网络网站，如 Facebook 和 Windows Live。
    
- Professional LinkedIn 等网络站点。
    
- 用于网络的其他业务线应用程序或公司内部网站。
    
术语"好友"通常用于包括好友、家庭、同事、连接以及 Office 用户在协作上下文（如 SharePoint）中关联或已添加到用户的社交网络帐户的任何人。 非好友是好友活动更新中引用的人，但不是已添加到好友Office用户的社交网络帐户的好友。 联系人是联系人文件夹中Outlook人员。 
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

