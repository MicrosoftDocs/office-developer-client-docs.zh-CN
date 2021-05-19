---
title: 功能的 XML
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: edad1223-a55f-4e4a-8e90-3471f2f559ac
description: OSC (XML 架构) capabilities 元素允许 OSC 提供程序指定其功能。 此类功能包括：
ms.openlocfilehash: ff6abbd4d99eb542a11e3d64a2015fc0585fca79
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435003"
---
# <a name="xml-for-capabilities"></a>功能的 XML

OSC (XML 架构) **capabilities** 元素允许 OSC 提供程序指定其功能。 此类功能包括： 
  
- 提供程序是否支持从社交网络获取、缓存或动态查找好友和活动。
    
- OSC 应如何显示某些登录用户界面。
    
- OSC 是应该使用基于表单的身份验证，还是自动配置社交网络和社交网络上的用户日志。
    
功能的 XML **架构** 至关重要，因为它向 OSC 标识提供程序支持的功能。 OSC 提供程序必须实现返回结果字符串的 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)_方法。_ OSC 调用 **ISocialProvider：：GetCapabilities** 以获取有关结果字符串中 OSC 提供程序的功能的信息，这符合 **capabilities** 元素的 XML 架构定义。 此信息使从 OSC 到 OSC 提供程序的后续调用能够正常运行。 
  
若要将 OSC 提供程序的功能指定为 **ISocialProvider：：GetCapabilities** 方法的输出参数，必须符合 OSC 提供程序扩展性 XML 架构。 下图显示了 **功能** XML 结构。 
  
**图 1. \<capabilities \> XML 结构**

![功能 XML 结构](media/ol14oscref_Specifyingxmlforcapabilities_image1.gif)
  
有关 **capabilities** 元素的子元素的详细说明，请参阅 [Capabilities XML Elements。](capabilities-xml-elements.md) 有关功能 XML **的示例** ，请参阅 [Capabilities XML Example](capabilities-xml-example.md)。 有关 OSC 提供程序 XML 架构的完整定义，包括哪些元素是必需的或可选的，请参阅Outlook[连接器提供程序 XML 架构。](outlook-social-connector-provider-xml-schema.md)
  
## <a name="see-also"></a>另请参阅

- [Capabilities XML 示例](capabilities-xml-example.md)  
- [同步好友和活动](synchronizing-friends-and-activities.md)  
- [好友 XML](xml-for-friends.md)  
- [活动的 XML](xml-for-activities.md)
- [使用 OSC XML 架构开发提供程序](developing-a-provider-with-the-osc-xml-schema.md)

