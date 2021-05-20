---
title: 支持邮件存储中的Read-Only和视图
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da5f080d-4397-4ce6-8561-73dd13445e77
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0b7ffe07278cfcbba95351f2720e427dd8500221
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432427"
---
# <a name="supporting-forms-and-views-in-read-only-message-stores"></a>支持邮件存储中的Read-Only和视图

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件存储提供程序允许对基础存储机制具有只读权限，则客户端应用程序和 MAPI 表单管理器将无法执行某些操作。 具体而言，客户端将无法添加或修改自定义视图，MAPI 表单管理器将无法在存储文件夹的关联内容表中安装表单。
  
对于许多只读邮件存储，这可能不是问题。 如果是这种情况，则邮件存储提供程序完全不需要支持关联的内容表。 但是，如果邮件存储提供程序必须是只读的，并且它还必须支持一组预定义的视图或表单，则需要支持关联的内容表。
  
为此，最常见的策略是让邮件存储提供程序将它们硬编码到邮件存储中，因为客户端和 MAPI 表单管理器无法将视图或表单安装到邮件存储中。 这意味着，任何客户端或 MAPI 表单管理器访问邮件存储时，包含视图或表单的关联内容表将存在于邮件存储中。 然后，当客户端请求关联内容表以从表单获取自定义视图或 MAPI 表单管理器请求关联内容表以启动表单时，邮件存储提供程序可以提供一个。 
  
创建邮件存储本身时，需要创建和填充关联的内容表这一要求意味着邮件存储提供程序需要获取有关客户端和 MAPI 表单管理器用于存储视图和表单的特殊邮件的格式的信息。 这些格式是什么将取决于所使用的客户端和 MAPI 表单管理器，因此此处无法提供这些格式的说明。
  
## <a name="see-also"></a>另请参阅



[只读邮件存储](read-only-message-stores.md)

