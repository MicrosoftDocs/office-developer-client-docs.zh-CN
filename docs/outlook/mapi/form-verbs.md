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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424026"
---
# <a name="form-verbs"></a>表单谓词

**适用于**：Outlook 2013 | Outlook 2016 
  
窗体的用户界面通常提供菜单项或控件，使用户能够对表单执行某种操作。 表单服务器的作业用于处理这些用户操作。 此接口使用标准 Win32 API 实现;编写一个就像为常规 Win32 程序编写其他接口一样。
  
通常，用户操作与动词关联。 动词是特定于特定邮件类的操作的名称。 例如 **，Reply** 是由许多表单服务器实现的一个动词，每个窗体服务器对此动词的解释可能不同。 动词有时称为命令。 
  
> [!NOTE]
> 并非窗体上的所有菜单项和控件都与动词相对应。 例如，" **取消"** 按钮与窗体服务器中的"取消"动作不对应。 通常，动词与特定于特定邮件类或一组邮件类的操作相关联。 尽管不同的邮件类可以支持不同的动词集，但所有邮件类都至少支持 Open 动词，该动词显示窗体的用户界面，并加载该窗体的属性值。 
  
动词可以不带任何参数。 使用变量参数导出命令的表单必须使用自动化机制。
  
客户端可以通过 [IMAPIFormInfo：：CalcVerbSet](imapiforminfo-calcverbset.md) 方法确定特定邮件类支持哪些谓词，该方法由 MAPI 表单管理器实现。 表单管理器从表单的配置文件获取此信息。 客户端使用此方法返回的动词集向用户显示可以在邮件上执行哪些命令。 例如，客户端可能允许用户在邮件上单击鼠标右键以显示适用于该消息的动词。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

