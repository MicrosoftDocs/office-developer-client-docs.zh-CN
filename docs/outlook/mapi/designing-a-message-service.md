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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316721"
---
# <a name="designing-a-message-service"></a>设计邮件服务

**适用于**：Outlook 2013 | Outlook 2016 
  
在开始编写代码以支持邮件服务之前, 一定要创建设计。 在设计过程中解决以下问题:
  
1. 确定邮件服务中应包含多少个服务提供程序。 在服务中仅包括相关的服务提供程序 (即, 适用于同一邮件系统的提供程序)。 不相关的服务提供程序不属于同一邮件服务。 使用用于集成不相关服务提供程序和邮件服务的配置文件。
    
2. 确定邮件服务中应包含哪种类型的服务提供商。 大多数 messge 服务包括每个通用类型的一个提供程序。 也就是说, 典型的邮件服务有一个通讯簿提供程序、一个邮件存储提供程序和一个传输提供程序。
    
3. 确定应包含邮件服务的 dll 的数目。 邮件服务使用的 dll 数取决于以下各项:
    
   - 您作为邮件服务编写者的复杂程度愿意处理。
    
   - 邮件服务中的服务提供程序的类型。
    
   - 邮件服务可能与另一邮件服务之间的关系。
    
   由于 MAPI 仅存储每个提供程序类型的一个入口点, 因此在一个 DLL 中不包含同一类型的多个提供程序。 如果有必要包含一种类型的多个提供程序, 可以在单独的 dll 中实现它们, 也可以让它们共享入口点函数。 另一种方法是在一个 DLL 中实现相关的邮件服务, 或者可以使用相同的安装和配置代码和同一个 dll 入口点函数的邮件服务。
    
   如果可能, 请将其简化并使用一个 DLL, 其中包含邮件服务中所有服务提供程序的实现以及要安装和配置邮件服务的所有代码。 如果不能这样做, 则可以为安装和配置代码实现一个 dll, 为所有服务提供程序实现一个 dll, 为每个提供程序实现一个 dll。
    
4. 确定邮件服务 DLL 或 dll 的名称。 
    
## <a name="see-also"></a>另请参阅

- [邮件服务实现](message-service-implementation.md)

