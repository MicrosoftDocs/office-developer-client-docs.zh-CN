---
title: 设计邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 32627ebb-547f-4fac-a406-e7243ec5521b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 19a8a939685c440901f3f57d72baf673a579e590
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404293"
---
# <a name="designing-a-message-service"></a>设计邮件服务

**适用于**：Outlook 2013 | Outlook 2016 
  
在开始编写代码以支持邮件服务之前，创建设计非常重要。 解决设计过程中以下问题：
  
1. 确定邮件服务中应包含多少个服务提供程序。 仅包括相关服务提供商 (，即与服务中相同的邮件系统) 提供程序。 不相关的服务提供程序不属于同一邮件服务。 使用配置文件集成不相关的服务提供程序和邮件服务。
    
2. 确定邮件服务中应包含哪些类型的服务提供程序。 大多数混乱服务包括每种常见类型的一个提供程序。 也就是说，典型的邮件服务有一个通讯簿提供程序、一个邮件存储提供程序和一个传输提供程序。
    
3. 确定应包含邮件服务的 DLL 数量。 邮件服务使用的 DLL 数量取决于以下各项：
    
   - 您作为邮件服务的编写者愿意处理的复杂性。
    
   - 邮件服务中的服务提供程序的类型。
    
   - 邮件服务可能与另一个邮件服务的关系。
    
   由于 MAPI 只存储每个提供程序类型的一个入口点，因此在单个 DLL 中不要包括同一类型的多个提供程序。 如果包含一种类型的多个提供程序是有意义的，则要么在单独的 DLL 中实现它们，要么让它们共享入口点函数。 另一个选项是，在一个 DLL 中实现能够使用相同的安装和配置代码以及同一 DLL 入口点函数的相关邮件服务或邮件服务。
    
   如果可能，请保持简单，并使用一个 DLL，其中包含邮件服务中所有服务提供程序的实现以及安装和配置邮件服务的所有代码。 如果不可能，您可以为安装和配置代码实现一个 DLL，并针对所有服务提供程序实现一个 DLL，或者为每个提供程序实现一个 DLL。
    
4. 确定邮件服务 DLL 或 DLL 的名称。 
    
## <a name="see-also"></a>另请参阅

- [邮件服务实现](message-service-implementation.md)

