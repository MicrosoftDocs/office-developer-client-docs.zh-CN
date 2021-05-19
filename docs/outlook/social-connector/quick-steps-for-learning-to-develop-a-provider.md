---
title: 学习开发提供程序的快速步骤
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13c0ae8c-d268-4bf0-942d-2a6160142f5e
description: 本主题推荐了几个步骤，以了解如何在 OSC Outlook提供程序 (社交) 连接器。
ms.openlocfilehash: 581997ab257d59062761d97bfef49a88b90bb1e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424215"
---
# <a name="quick-steps-for-learning-to-develop-a-provider"></a>学习开发提供程序的快速步骤

若要开发 OSC 提供程序，您需要完成以下常规步骤：
  
- 实现四个强制接口：ISocialProvider、ISocialSession、ISocialProfile 和[ISocialPerson。](isocialpersoniunknown.md) [](isocialprovideriunknown.md) [](isocialsessioniunknown.md) [](isocialprofileisocialperson.md) 根据社交网络对缓存登录凭据、跟踪社交网络上的人员或动态同步好友及其活动的支持，您可能需要实现 [ISocialSession2](isocialsession2iunknown.md) 接口。 
    
- 与实现接口并行，测试和调试 OSC 提供程序。 

- 部署 OSC 提供程序。  

- 在发布前执行最终测试。
    
## <a name="step-a-implementing-interfaces"></a>步骤 A：实现接口

OSC 提供程序实现接口，以便 OSC 可以通过 OSC 提供程序使用这些接口获取有关社交网络或从社交网络获取必要信息。 这些信息包括：
  
- 如何向用户显示帐户登录对话框。    
- 提供程序是否支持在社交网络上显示好友或活动。    
- 如何在联系人卡片或联系人窗格中显示好友Outlook活动。     
- 何时刷新联系人卡片或人员窗格上的好友或活动信息。
    
该信息通常以 XML 字符串形式作为接口方法的输出参数从提供程序传递到 OSC。 OSC 和 OSC 提供程序均符合 OSC 提供程序 XML 架构。 因此，在实施接口的过程中，您需要深入了解 XML 架构如何允许您指定上面列出的信息。 

以下资源说明如何为提供程序功能、好友和活动指定 XML：
  
- [OSC 典型调用序列](osc-typical-calling-sequences.md)    
- [同步好友和活动](synchronizing-friends-and-activities.md)    
- [Capabilities XML 示例](capabilities-xml-example.md)   
- [功能的 XML](xml-for-capabilities.md)    
- [好友 XML 示例](friends-xml-example.md)    
- [好友 XML](xml-for-friends.md)   
- [活动源 XML 示例](activity-feed-xml-example.md)   
- [活动的 XML](xml-for-activities.md)
    
在开始实现之前，还请查阅以下主题，以便以后在调试过程中节省时间：
  
- [技术要求](technical-requirements.md)    
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)    
- [OSC 示例模板](osc-sample-templates.md)
    
## <a name="step-b-debugging"></a>步骤 B：调试

调试 [提供程序主题](debugging-a-provider.md) 建议了在开发 OSC 提供程序时可以使用的调试过程。 
  
在开发时，还可以参阅准备发布 [OSC](getting-ready-to-release-an-osc-provider.md) 提供程序，以更好地了解在某些情况下的预期行为 (例如基本身份验证和基于表单的身份验证) 。 
  
## <a name="step-c-deploying"></a>步骤 C：部署

请参阅以下主题以了解部署要求：
  
- [部署提供程序](deploying-a-provider.md)    
- [注册提供程序](registering-a-provider.md)   
- [安装清单](installation-checklist.md)
    
## <a name="step-d-final-testing-before-release"></a>步骤 D：发布前的最终测试

根据社交网络和 OSC 提供程序，在发布提供程序之前，通常应执行特定于提供程序的测试。 有关建议的测试列表，请参阅准备发布 [OSC 提供程序](getting-ready-to-release-an-osc-provider.md)。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

