---
title: 功能的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: edad1223-a55f-4e4a-8e90-3471f2f559ac
description: Capabilities 元素 (OSC) 提供程序的 XML 架构中允许 OSC 提供程序指定其功能。 此类功能包括以下组件：
ms.openlocfilehash: 8192c4d559ae656cfc3b12cd8f50f7d4acd5ed5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779330"
---
# <a name="xml-for-capabilities"></a>功能的 XML

**Capabilities**元素 (OSC) 提供程序的 XML 架构中允许 OSC 提供程序指定其功能。 此类功能包括以下组件： 
  
- 是否提供程序支持获取、 缓存，或动态查找朋友和活动从社交网络。
    
- 如何 OSC 应显示特定登录用户界面。
    
- 是否 OSC 应该使用基于表单的身份验证或自动配置的社交网络和日志上社交网络上的用户。
    
**功能**的 XML 架构非常重要，因为它标识 OSC 提供程序支持的功能。 OSC 提供程序必须实现[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)方法返回_结果_字符串。 OSC 调用**ISocialProvider::GetCapabilities**获取 OSC 提供程序_结果_字符串，符合**capabilities**元素的 XML 架构定义中的功能有关的信息。 此信息允许对后续调用从 OSC OSC 提供程序才能正常运行。 
  
若要作为**ISocialProvider::GetCapabilities**方法的输出参数指定 OSC 提供程序的功能，必须符合 OSC 提供程序扩展性 XML 架构。 下图显示了**功能**XML 结构。 
  
**图 1。\<功能\>XML 结构**

![功能 XML 结构](media/ol14oscref_Specifyingxmlforcapabilities_image1.gif)
  
**Capabilities**元素的子元素的详细说明，请参阅[功能 XML 元素](capabilities-xml-elements.md)。 **功能**XML 的示例，请参阅[功能 XML 示例](capabilities-xml-example.md)。 有关完整定义 OSC 提供程序 XML 架构，其中包括哪些元素必需或可选的请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。
  
## <a name="see-also"></a>另请参阅

- [功能 XML 示例](capabilities-xml-example.md)  
- [同步朋友和活动](synchronizing-friends-and-activities.md)  
- [朋友 XML](xml-for-friends.md)  
- [活动的 XML](xml-for-activities.md)
- [开发 OSC XML 架构的提供程序](developing-a-provider-with-the-osc-xml-schema.md)

