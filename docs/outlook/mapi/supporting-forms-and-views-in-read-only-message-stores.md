---
title: 支持只读邮件存储区中的表单和视图
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da5f080d-4397-4ce6-8561-73dd13445e77
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ef9b85fd8dad980f92f5e06a4b54daf146fbcec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778913"
---
# <a name="supporting-forms-and-views-in-read-only-message-stores"></a>支持只读邮件存储区中的表单和视图

  
  
**适用于**： Outlook 
  
如果您的消息存储提供程序允许对基础存储机制的只读权限，客户端应用程序和 MAPI 窗体管理器将无法执行某些操作。 具体而言，将无法添加或修改自定义视图，客户端和 MAPI 窗体管理器将不能安装关联的内容存储的文件夹的表中的表单。
  
对于许多只读消息存储，可能不出现问题。 如果是这样，则不需要在所有支持关联的内容表的消息存储提供程序。 但是，如果您的消息存储提供程序必须是只读的并且它还必须支持一组预定义的视图或表单，它将需要支持关联的内容的表格。
  
这样，客户端和 MAPI 窗体管理器无法安装视图或窗体插入邮件存储，因为的最常见策略是硬编码的消息存储提供程序它们到邮件存储区。 这意味着或多个关联的内容包含视图或窗体的表将存在于消息存储库创建时，任何客户端或 MAPI 之前窗体管理器以往访问它。 然后，在客户端请求从窗体中获取自定义视图关联的内容表或 MAPI 窗体管理器请求相关联的内容表格，以启动窗体时，消息存储提供程序可以提供一个。 
  
关联的内容表的创建和填充时创建邮件存储本身此要求意味着您的消息存储提供程序需要该客户端和 MAPI 窗体获得的特殊的消息的格式信息用于存储视图和窗体管理器。 什么是这些格式将取决于客户端和 MAPI 窗体管理器被使用，以便无法此处提供的说明。
  
## <a name="see-also"></a>另请参阅



[只读邮件存储区](read-only-message-stores.md)

