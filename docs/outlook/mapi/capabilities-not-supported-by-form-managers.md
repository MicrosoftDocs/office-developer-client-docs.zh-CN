---
title: 表单管理器不支持的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b51e9e03-a333-4fdc-b6fe-87bd4e947b9f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e31eacaae54968fbdbd9fe0345130a8d09c3509f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326374"
---
# <a name="capabilities-not-supported-by-form-managers"></a>表单管理器不支持的功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于性能原因, 默认表单管理器不支持以下功能, 但自定义表单管理器可能支持以下功能。
  
- 使表单能够在表单库中进行分组或分类的层次结构。 表单库是表单的平面文件数据库。
    
- 与邮件类或超类对应的窗体类别的访问控制。
    
- 在一个表单库中支持同一表单的多个语言版本。
    
这些是实施问题。 无需阻止自定义表单管理器实现这些功能。
  
MAPI 表单体系结构不支持同时运行多个表单管理器。 虽然 MAPI 支持多个并发邮件存储提供程序、传输提供程序和通讯簿提供程序, 但只有一个表单管理器受支持。
  
由于一次只能运行一个表单管理器, 因此如果实现自定义表单管理器, 则必须重新实现所需的默认表单管理器中的任何功能。 由于自定义表单管理器将完全替换默认表单管理器, 因此默认表单管理器的功能将不可用, 除非它们在自定义表单管理器中重复。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

