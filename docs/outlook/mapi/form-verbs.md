---
title: 窗体谓词
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a63bf0a7-24e6-4eef-98e8-3744ce5f9f2d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1ecc80feec2b0a86f35d03f1ca4f75ea9ff094e4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774969"
---
# <a name="form-verbs"></a>窗体谓词

**适用于**： Outlook 
  
窗体的用户界面通常提供菜单项或允许用户执行某些类型的操作与窗体的控件。 它是窗体服务器的作业处理这些用户操作。 使用标准 Win32 Api; 实现此接口写入一就如同编写正则 Win32 程序其他接口。
  
通常，用户操作是与动作相关联。 动词是特定于特定邮件类别的操作的名称。 例如，**答复**是动作的由许多窗体服务器，其中每个可能的不同的解释实现动词。 动词有时称为命令。 
  
> [!NOTE]
> 并非所有的菜单项和窗体上的控件对应于动词。 例如，**取消**按钮不对应于窗体服务器内取消动词。 通常，谓词是与特定于特定的邮件类或一组的邮件类的操作关联。 尽管不同邮件类可以支持不同的谓词集，所有至少支持打开动作，其中显示窗体的用户界面和消息的属性值加载它。 
  
动词可能不带任何参数。 窗体的导出命令与变量参数必须使用自动化机制。
  
客户端可以确定哪些谓词通过[IMAPIFormInfo::CalcVerbSet](imapiforminfo-calcverbset.md)方法，由 MAPI 窗体管理器实现支持的特定邮件类别。 窗体管理器从窗体的配置文件中获取此信息。 客户端使用此方法返回的动词集显示一条消息，可执行的命令的用户。 例如，客户端可能会使用户能够通过要显示动词不适用于该邮件的消息中单击鼠标右键。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 表单](mapi-forms.md)

