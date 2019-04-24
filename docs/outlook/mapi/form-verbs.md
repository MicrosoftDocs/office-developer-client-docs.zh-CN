---
title: 表单谓词
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a63bf0a7-24e6-4eef-98e8-3744ce5f9f2d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: dbd08437dfdd38c3a43cbf12eae8710cc8e3661e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327487"
---
# <a name="form-verbs"></a>表单谓词

**适用于**：Outlook 2013 | Outlook 2016 
  
窗体的用户界面通常提供了菜单项或控件, 使用户能够对窗体执行某种类型的操作。 处理这些用户操作的表单服务器作业。 此接口是使用标准 Win32 api 实现的;编写一个规则就像为常规的 Win32 程序编写其他接口一样。
  
通常, 用户操作与谓词相关联。 动词是特定于特定邮件类别的操作的名称。 例如, **Reply**是一个由多个表单服务器实现的动词, 每个表单服务器可能对该动词有不同的解释。 谓词有时也称为命令。 
  
> [!NOTE]
> 并非所有菜单项和窗体上的控件都对应于一个谓词。 例如, "**取消**" 按钮不对应于表单服务器中的取消谓词。 通常, 谓词与特定的邮件类或一组邮件类的操作相关联。 虽然不同的邮件类可以支持不同的谓词集, 但它们都至少支持打开谓词, 该谓词显示窗体的用户界面, 并使用邮件的属性值加载该窗体。 
  
动词可能不带任何参数。 导出带变量参数的命令的表单必须使用自动化机制。
  
客户端可以通过[IMAPIFormInfo:: CalcVerbSet](imapiforminfo-calcverbset.md)方法 (由 MAPI 表单管理器实现) 确定特定邮件类别支持的动词。 表单管理器从表单的配置文件中获取此信息。 客户端使用此方法返回的谓词集向用户显示可对邮件执行哪些命令。 例如, 客户端可以让用户在邮件上单击鼠标右键, 以显示适用于该邮件的谓词。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

