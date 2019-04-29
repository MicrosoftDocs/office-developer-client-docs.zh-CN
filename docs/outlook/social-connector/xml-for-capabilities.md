---
title: 功能的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: edad1223-a55f-4e4a-8e90-3471f2f559ac
description: '(.osc) 提供程序 XML 架构中的 "功能" 元素允许 .osc 提供程序指定其功能。 此类功能包括以下内容:'
ms.openlocfilehash: ff6abbd4d99eb542a11e3d64a2015fc0585fca79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435003"
---
# <a name="xml-for-capabilities"></a>功能的 XML

(.osc) 提供程序 XML 架构中的 "**功能**" 元素允许 .osc 提供程序指定其功能。 此类功能包括以下内容: 
  
- 提供程序是否支持从社交网络获取、缓存或动态查找好友和活动。
    
- .osc 应如何显示某些登录用户界面。
    
- .osc 是否应使用基于表单的身份验证, 或自动配置社交网络上的用户的社交网络和日志。
    
**功能**的 XML 架构非常关键, 因为它会将提供程序支持的功能标识为 .osc。 一个 .osc 提供程序必须实现[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)方法, 该方法返回_结果_字符串。 .osc 调用**ISocialProvider:: GetCapabilities**获取有关在_结果_字符串中的 .osc 提供程序的功能的信息, 该信息符合**功能**元素的 XML 架构定义。 此信息支持从 .osc 到 .osc 提供程序的后续呼叫正常运行。 
  
若要将 .osc 提供程序的功能指定为**ISocialProvider:: GetCapabilities**方法的输出参数, 您必须符合 .osc 提供程序扩展性 XML 架构。 下图显示了 XML 结构的**功能**。 
  
**图1。\<功能\> XML 结构**

![功能 XML 结构](media/ol14oscref_Specifyingxmlforcapabilities_image1.gif)
  
有关 "**功能**" 元素的子元素的详细说明, 请参阅[功能 XML 元素](capabilities-xml-elements.md)。 有关 XML 的**功能**示例, 请参阅[功能 xml 示例](capabilities-xml-example.md)。 有关 .osc 提供程序 XML 架构的完整定义 (包括哪些元素是必需元素或可选的元素), 请参阅[Outlook Social Connector 提供程序 XML 架构](outlook-social-connector-provider-xml-schema.md)。
  
## <a name="see-also"></a>另请参阅

- [功能 XML 示例](capabilities-xml-example.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md)  
- [适用于好友的 XML](xml-for-friends.md)  
- [适用于活动的 XML](xml-for-activities.md)
- [使用 .osc XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

