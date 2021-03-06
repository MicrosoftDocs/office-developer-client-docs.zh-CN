---
title: MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 855292b8-028e-4c1e-87ed-3f20b9ba584a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3c95f6a1d4d50dd6552c6e786d17c40da14f3f3c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419105"
---
# <a name="mapi-form-servers"></a>MAPI 表单服务器

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从用户的角度来看，窗体通常是属性表信息或数据输入表单（使用户能够输入结构化信息）的表单。 但是，它可以是任何与邮件类关联的用户界面。 从程序员的角度来看，表单包含：
  
- 具有自己的邮件类和 OLE 标识符的 MAPI 邮件类型。
    
- 实现表单服务器的可执行文件。
    
- 表单服务器使用的 MAPI 属性的集合（自定义或其他属性）。 邮件客户端可以使用其中某些或全部功能。
    
- 描述表单并且由表单管理器使用的配置文件。
    
由于表单是 [IMessage](imessageimapiprop.md) 对象，因此它们呈现与 MAPI 邮件对象一致的属性和行为。 但是，由于表单可以具有特定于应用程序的自定义属性、控件和显示呈现，因此表单使用的 MAPI 接口足够通用，足以允许所需的任何界面。 表单的实际定义存储在表单库中，本节稍后将对此进行讨论。 
  
> [!NOTE]
> 更精确地说，所有消息都是 MAPI 表单的实例。 但是，通常更容易将自定义窗体视为邮件的特殊情况，因为用于撰写和阅读典型电子邮件的窗体是最常用的窗体。 所有邮件实际上只是窗体这一事实使自定义窗体与 MAPI 系统中任何其他邮件的状态相同。 
  
每个窗体都有一组属性，其中一些属性在表单的用户界面中可见。 通常，属性与表单用户界面中的字段匹配。 例如，采购订单窗体可能包含"项目、说明、价格、税款"和"分类汇总"字段。 这些字段只是同名表单属性的可视化呈现。 客户端通过 [IMAPIFormInfo：：CalcFormPropSet](imapiforminfo-calcformpropset.md) 方法确定特定邮件类支持的属性，该方法由 MAPI 表单管理器实现。 
  
与基本邮件一样，MAPI 窗体可以包含所有标准邮件属性，如发件人、目标收件人以及邮件发送时间。 窗体还可以包含任意数目的特定于窗体的自定义属性。 例如，"Bug 报告"表单可能包含 Bug 类型、Bug 严重性和产品版本的自定义属性。
  
若要创建表单，您必须实现一个表单服务器。 窗体服务器是一个可执行文件，当邮件客户端需要显示窗体服务器支持的类型的邮件时，将加载该文件。 反过来，表单服务器会创建表单对象，以显示特定消息和处理用户与这些消息的交互。
  
每个表单服务器都有一个与之关联的配置文件。 此文件包含描述表单服务器以表单管理器为优势的信息。 在将表单服务器安装到表单库中时，表单管理器会使用此信息。
  
有关创建表单的各个部分的详细信息，请参阅 Developing [MAPI Form Servers。](developing-mapi-form-servers.md)
  
表单服务器遵循组件对象模型 (COM) 。 表单服务器作为独立可执行文件运行，而不是作为过程内服务器运行。 有关详细信息，请参阅 ActiveX SDK 中的 COM 和 Windows 对象服务部分。
  
CLSID (一个) 标识符，用于标识每个表单服务器。 类标识符及其消息类之间始终存在一对一映射。 但是，这并不意味着表单服务器只能处理一个邮件类的邮件。 如果没有可供窗体服务器为特定类的邮件提供服务，则所使用的表单管理器应尝试在邮件类层次结构中查找邮件类的窗体服务器;随 SDK 提供的默认表单Windows可进行此操作。 此类表单服务器可能只能呈现邮件属性的子集 (类应用程序支持的属性，) 比不呈现好。 如果找不到匹配的表单服务器，会发生什么情况是特定于所使用的表单管理器的实现详细信息;当发生这种情况时，默认表单管理器不会打开邮件。
  
有关详细信息，请参阅 [MAPI Message Classes](mapi-message-classes.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

