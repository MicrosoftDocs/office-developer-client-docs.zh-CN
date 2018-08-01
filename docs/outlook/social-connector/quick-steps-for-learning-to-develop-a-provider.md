---
title: 学习开发提供程序的快速步骤
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13c0ae8c-d268-4bf0-942d-2a6160142f5e
description: 本主题提供了几个步骤，若要了解有关开发 Outlook Social Connector (OSC) 提供程序。
ms.openlocfilehash: 345e8600c704504be091ee23c66b7f85575cde90
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779327"
---
# <a name="quick-steps-for-learning-to-develop-a-provider"></a>学习开发提供程序的快速步骤

若要开发 OSC 提供程序，您需要完成以下一般步骤：
  
- 实现四个强制接口： [ISocialProvider](isocialprovideriunknown.md)、 [ISocialSession](isocialsessioniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)和[ISocialPerson](isocialpersoniunknown.md)。 根据您的社交网络支持缓存社交网络中，或动态同步朋友和其活动，关注人员的登录凭据，您可能想要实现[ISocialSession2](isocialsession2iunknown.md)接口。 
    
- 在实现接口的同时，测试和调试 OSC 提供程序。 

- 部署 OSC 提供程序。  

- 执行操作之前版本的最终测试。
    
## <a name="step-a-implementing-interfaces"></a>步骤答： 实现接口

OSC 提供程序实现接口，以便 OSC 可以使用这些接口以获取有关或从社交网络中，通过 OSC 提供程序所需的信息。 此类信息包括以下组件：
  
- 如何向用户显示帐户登录对话框。    
- 是否提供程序支持显示朋友或活动显示社交网络上。    
- 如何在联系人卡片或 Outlook 人员窗格中显示朋友和活动。     
- 何时刷新朋友或活动信息的联系人卡片或人员窗格。
    
信息通常传递从提供程序给 OSC，作为接口方法的输出参数的 XML 字符串的形式。 OSC 和 OSC 提供程序符合 OSC 提供程序的 XML 架构。 因此，在过程中实现的接口，您需要的 XML 架构如何允许您指定的信息，如上面列出更好地理解。 

以下资源介绍如何指定提供程序功能、 朋友和活动的 XML:
  
- [OSC 典型调用序列 （英文)](osc-typical-calling-sequences.md)    
- [同步朋友和活动](synchronizing-friends-and-activities.md)    
- [功能 XML 示例](capabilities-xml-example.md)   
- [功能 XML](xml-for-capabilities.md)    
- [朋友 XML 示例](friends-xml-example.md)    
- [朋友 XML](xml-for-friends.md)   
- [活动源的 XML 示例](activity-feed-xml-example.md)   
- [活动的 XML](xml-for-activities.md)
    
开始实施之前，还请参考以下主题以节省时间更高版本中调试过程：
  
- [技术要求](technical-requirements.md)    
- [开发提供程序的最佳做法](best-practices-for-developing-a-provider.md)    
- [OSC 示例模板](osc-sample-templates.md)
    
## <a name="step-b-debugging"></a>步骤 b： 调试

主题[调试提供程序](debugging-a-provider.md)建议调试开发 OSC 提供程序时，可以使用的过程。 
  
时要开发，您还可以参考[获取准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)获得更好地了解在某些方案 （例如，基本和基于表单的身份验证） 的预期行为。 
  
## <a name="step-c-deploying"></a>步骤 c： 部署

请参阅以下主题以了解如何部署要求：
  
- [部署提供程序](deploying-a-provider.md)    
- [注册提供程序](registering-a-provider.md)   
- [安装清单](installation-checklist.md)
    
## <a name="step-d-final-testing-before-release"></a>步骤 d： 最终版本之前测试

根据您的社交网络和 OSC 提供程序，有通常特定于提供程序测试释放您的提供商之前应执行。 测试的建议列表，请参阅[入门准备发布 OSC 提供程序](getting-ready-to-release-an-osc-provider.md)。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

