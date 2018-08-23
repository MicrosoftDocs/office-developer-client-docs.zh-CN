---
title: 表单管理器不支持的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b51e9e03-a333-4fdc-b6fe-87bd4e947b9f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a84c0a93f80080b71f6049e73f0a0094c38c28ef
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566871"
---
# <a name="capabilities-not-supported-by-form-managers"></a>表单管理器不支持的功能

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
以下功能不受支持的默认窗体管理器出于性能原因，但可以支持的自定义窗体经理。
  
- 使窗体进行分组或整个表单库分类层次结构。 表单库是平面文件数据库的窗体。
    
- 类别的窗体，邮件类或超类对应的访问控制。
    
- 支持的单个窗体库中同一窗体的多个语言版本。
    
这些是实现问题。 没有任何限制阻止自定义窗体管理器实现这些功能。
  
MAPI 表单体系结构不支持同时运行的多个窗体管理器。 尽管 MAPI 支持多个并发消息存储提供程序、 传输提供程序和通讯簿提供程序，支持单个窗体管理器。
  
由于只有一个窗体管理器可能同时运行，如果您实现自定义窗体管理器，必须重新实现所需的默认窗体管理器从任何功能。 因为您的自定义窗体管理器将完全替换默认窗体管理器，默认窗体管理器的功能将不可用，除非他们在您的自定义窗体管理器重复。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

