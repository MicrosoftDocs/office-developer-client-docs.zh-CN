---
title: 学习开发提供程序的快速步骤
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 13c0ae8c-d268-4bf0-942d-2a6160142f5e
description: 本主题建议几个步骤来了解如何开发 Outlook Social Connector (.osc) 提供程序。
ms.openlocfilehash: 581997ab257d59062761d97bfef49a88b90bb1e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424215"
---
# <a name="quick-steps-for-learning-to-develop-a-provider"></a>学习开发提供程序的快速步骤

若要开发一个 .osc 提供程序, 您需要完成以下常规步骤:
  
- 实现四个强制接口: [ISocialProvider](isocialprovideriunknown.md)、 [ISocialSession](isocialsessioniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)和[ISocialPerson](isocialpersoniunknown.md)。 根据社交网络对缓存登录凭据的支持、关注社交网络的人员或动态同步好友及其活动, 您可能希望实现[ISocialSession2](isocialsession2iunknown.md)接口。 
    
- 与实现接口并行, 测试和调试 .osc 提供程序。 

- 部署 .osc 提供程序。  

- 请先进行最终的测试, 然后再发布。
    
## <a name="step-a-implementing-interfaces"></a>步骤 A: 实现接口

一个 .osc 提供程序实现接口, 以便 .osc 可以通过 .osc 提供程序使用这些接口获取社交网络的必要信息。 此类信息包括以下内容:
  
- 如何向用户显示 "帐户登录" 对话框。    
- 提供商是否支持显示在社交网络中显示的朋友或活动。    
- 如何在联系人卡片或 Outlook 人员窗格中显示好友和活动。     
- 何时刷新 "联系人卡片" 或 "人员" 窗格上的好友或活动信息。
    
信息通常以 XML 字符串形式的形式从提供程序传递给 .osc, 作为接口方法的输出参数。 .osc 和 .osc 提供程序都符合 .osc 提供程序 XML 架构。 因此, 在实现接口的过程中, 您需要充分了解 XML 架构如何允许您指定上面所列的信息。 

以下资源介绍了如何为提供程序功能、朋友和活动指定 XML:
  
- [.osc 典型调用序列](osc-typical-calling-sequences.md)    
- [同步好友和活动](synchronizing-friends-and-activities.md)    
- [功能 XML 示例](capabilities-xml-example.md)   
- [XML 的功能](xml-for-capabilities.md)    
- [友元 XML 示例](friends-xml-example.md)    
- [适用于好友的 XML](xml-for-friends.md)   
- [活动源 XML 示例](activity-feed-xml-example.md)   
- [适用于活动的 XML](xml-for-activities.md)
    
开始实施之前, 还请先参阅以下主题, 在调试过程的后续部分中节省时间:
  
- [技术要求](technical-requirements.md)    
- [开发提供程序的最佳实践](best-practices-for-developing-a-provider.md)    
- [.osc 示例模板](osc-sample-templates.md)
    
## <a name="step-b-debugging"></a>步骤 B: 调试

[调试提供程序](debugging-a-provider.md)的主题建议在开发 .osc 提供程序时可使用的调试过程。 
  
在开发过程中, 您还可以参考[准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md), 以便更好地了解特定场景中的预期行为 (例如, 基本身份验证和基于表单的身份验证)。 
  
## <a name="step-c-deploying"></a>步骤 C: 部署

若要了解部署要求, 请参阅以下主题:
  
- [部署提供程序](deploying-a-provider.md)    
- [注册提供程序](registering-a-provider.md)   
- [安装清单](installation-checklist.md)
    
## <a name="step-d-final-testing-before-release"></a>步骤 D: 发布前的最终测试

根据你的社交网络和 .osc 提供程序, 通常会在发布提供程序之前执行特定于提供程序的测试。 有关建议的测试列表, 请参阅 "[准备发布一个 .osc 提供程序](getting-ready-to-release-an-osc-provider.md)"。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序开发入门（英文）](getting-started-with-developing-an-outlook-social-connector-provider.md)

