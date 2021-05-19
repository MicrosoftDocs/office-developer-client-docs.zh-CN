---
title: 表单管理员不支持的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b51e9e03-a333-4fdc-b6fe-87bd4e947b9f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e31eacaae54968fbdbd9fe0345130a8d09c3509f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419378"
---
# <a name="capabilities-not-supported-by-form-managers"></a>表单管理员不支持的功能

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
由于性能原因，默认表单管理器不支持以下功能，但自定义表单管理器可以支持这些功能。
  
- 允许在整个表单库中对表单进行分组或分类的层次结构。 表单库是表单的平面文件数据库。
    
- 窗体类别的访问控制，对应于邮件类或超级类。
    
- 支持单个表单库中同一表单的多个语言版本。
    
这些是实现问题。 没有任何内容可以阻止自定义表单管理器实现这些功能。
  
MAPI 表单体系结构不支持多个同时运行的表单管理器。 尽管 MAPI 支持多个并发邮件存储提供程序、传输提供程序和通讯簿提供程序，但仅支持一个表单管理器。
  
由于一次只能运行一个表单管理器，因此，如果实现自定义表单管理器，您必须重新实现默认表单管理器中所需的任何功能。 由于您的自定义表单管理器将完全替换默认表单管理器，因此默认表单管理器的功能将不可用，除非自定义表单管理器中重复了这些功能。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

