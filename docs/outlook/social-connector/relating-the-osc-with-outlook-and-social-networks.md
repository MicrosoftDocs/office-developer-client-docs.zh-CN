---
title: 将 OSC 与 Outlook 和社交网络关联起来
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f33705cc-8add-42be-9d9f-f4e9245d83f5
description: Outlook Social Connector (OSC) 可以在 Office 联系人卡片和 Outlook 人员窗格活动、 状态或照片更新显示同事、 朋友，或要与任何人。
ms.openlocfilehash: 6dc6221b89eca5303e7cf6a201927659d4ac9107
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779331"
---
# <a name="relating-the-osc-with-outlook-and-social-networks"></a>将 OSC 与 Outlook 和社交网络关联起来

Outlook Social Connector (OSC) 可以在 Office 联系人卡片和 Outlook 人员窗格活动、 状态或照片更新显示同事、 朋友，或要与任何人。 默认情况下 OSC 显示 Outlook 电子邮件，附件，并从所选人员会议请求收到。 如果所选的人员和 Office 用户协作 SharePoint 网站上，OSC 还显示文档更新和 SharePoint 网站从其他网站活动。 Office 用户感兴趣的关联的上下文中，根据 Office 用户可以安装 OSC 提供程序的业务线应用程序、 内部企业网站或 professional 和社交网络站点，如 LinkedIn 各种Facebook 和 Windows Live。
  
若要支持在 Office 客户端应用程序之间共享功能，OSC 核心引擎实施 Office 的共享组件的一部分，人员窗格作为 Outlook 外接程序实现的。 若要使用 OSC，必须安装该客户端计算机上的 Outlook 并配置 Outlook 配置文件，以便 OSC 可以缓存联系人文件夹中的联系人的 Office 用户。 
  
OSC 提供程序组件对象模型 (COM) 允许 OSC 访问一种方式独立于每个社交网络的 Api 中的社交网络数据的 DLL。 OSC 提供程序 DLL 必须客户端计算机上本地安装。 社交网络的 OSC 提供程序连接 OSC，它是 Outlook 的一部分，Internet 上的社交网络。
  
OSC 提供程序必须实现一组接口，定义为 OSC 提供程序扩展性，与 OSC 进行通信的一部分。 可用作开放平台 OSC 提供程序扩展性。
  
OSC 提供程序体系结构允许多个提供程序使用 OSC 核心引擎和聚合社会性信息，如朋友和活动。 图 1 显示了 OSC 提供程序体系结构。
  
**图 1。Outlook Social Connector 提供程序体系结构**

![社交网络、OSC 提供程序、OSC 和 Office](media/off15OSCRef_Architecture.gif)
  
## <a name="terminology"></a>术语

在此 Outlook Social Connector 提供程序参考，社交网络用于引用以下类型的网站： 
  
- 如 SharePoint 的协作网站。
    
- Facebook 和 Windows Live 等的社交网络站点。
    
- 如 LinkedIn 专业的网络站点。
    
- 其他业务线应用程序或用于网络的公司内部网站。
    
术语朋友通常用于包括朋友、 家人、 同事、 连接和任何其他人的 Office 用户相关联 SharePoint，如协作上下文中或已添加到用户的社交网络帐户。 非朋友是朋友的活动更新中引用的人员，而不是朋友已添加到 Office 用户的社交网络帐户。 联系人是 Outlook 联系人文件夹中的人。 
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

