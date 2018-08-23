---
title: 设计的消息服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 32627ebb-547f-4fac-a406-e7243ec5521b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b572ebcec0a33d2134f4cf19b88e3132cbd47117
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581998"
---
# <a name="designing-a-message-service"></a>设计的消息服务

**适用于**： Outlook 2013 |Outlook 2016 
  
在开始编写代码以支持邮件服务之前，务必创建设计。 解决设计过程中的以下问题：
  
1. 确定应消息服务中包括多少服务提供商。 在服务中包括仅相关的服务提供程序 （即，提供程序使用相同的消息系统的）。 不相关的服务提供商不属于同一消息服务。 使用集成不相关的服务提供商和消息服务的配置文件。
    
2. 确定哪种类型的服务提供程序应包含在邮件服务。 大多数消息服务包括一个提供程序的每种常见的类型。 即典型的消息服务都有一个通讯簿提供程序、 一个消息存储提供程序和一个传输提供程序。
    
3. 确定多少 Dll 应包含邮件服务。 消息服务使用的 Dll 的数量取决于以下因素：
    
   - 您的邮件服务编写器作为愿意处理的复杂性程度。
    
   - 在消息服务的服务提供商的类型。
    
   - 邮件服务可能必须与其他消息服务的关系。
    
   因为 MAPI 存储每个提供程序类型的一个入口点，不包括多个提供程序类型相同的单个 DLL 中。 如果要包含的一种类型的多个提供程序意义，在单独的 Dll 中实现它们或者了这些共享入口点函数。 另一个选项是实现相关的消息服务或消息服务，可以使用相同的安装和配置代码和相同的 DLL 入口点一个 DLL 函数。
    
   如果可能，使其简单，并使用一个 DLL，其中包含消息服务中的所有服务提供程序和所有代码以安装和配置消息服务的实现。 如果此方法不可行，您可以实现的安装和配置代码和是所有服务提供商的单个 DLL 的一个动态链接库或每个提供程序的一个 DLL。
    
4. 确定动态链接库或 Dll 的消息服务的名称。 
    
## <a name="see-also"></a>另请参阅

- [邮件服务实现](message-service-implementation.md)

