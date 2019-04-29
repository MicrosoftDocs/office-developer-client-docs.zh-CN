---
title: 属性表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f3475206-0237-4b5b-8efd-abd5d5e0b6c3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3f1c6497a182231645691f669d8900d33b495503
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430047"
---
# <a name="property-sheet-implementation"></a>属性表实现

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性表是一个对话框, 用于显示对象的属性。 这些属性可以是只读的, 仅允许用户查看它们或读/写, 使用户能够进行更改。 属性表包含一个或多个称为 pages 的重叠子窗口。 每个页面都包含用于设置一组相关属性的控制窗口。 用户通过选择将相应页面带到属性表的前景的选项卡在页面之间导航。
  
服务提供程序必须实现属性表, 以显示与邮件服务中的配置相关的最少属性集。 如果允许更改这些邮件服务属性, 则可以允许客户端应用程序的用户 (如控制面板) 进行更改或以编程方式实现更改。 实现属性表以显示和编辑其他类型的属性是可选的。 
  
通常, 在以下情况下, 您需要显示属性表:
  
- 当客户端调用状态对象的[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法时。 
    
- MAPI 调用提供程序对象的登录方法时。
    
- 当 MAPI 调用提供程序的消息服务的入口点函数时。
    
传输提供程序还实现属性表以显示与邮件选项相关的属性, 通讯簿提供程序实现属性表以查看和编辑有关邮件用户和通讯组列表、高级搜索的详细信息条件, 以及用于输入新用户的模板。
  
您可以使用以下三种技术之一来创建属性表:
  
- 手动, 就像对待任何对话框一样。
    
- 通过使用 Windows SDK 中提供的 "属性表" 常见控件。
    
- 使用 MAPI 显示表。
    
提供程序应选择最后一个选项 (使用显示表创建属性表)。 这是最简单的选项, 因为它无需使用 Windows 用户界面。 
  
若要实现根据消息服务属性的显示表生成的属性表, 请使用以下过程:
  
1. 调用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)以打开当前配置文件中的节。 传递[MAPIUID](mapiuid.md)或 NULL 以打开提供程序的配置文件部分。 
    
2. 调用[CreateIProp](createiprop.md)以创建属性数据对象。 
    
3. 调用 profile 节的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将所有节的属性复制到属性数据对象。 
    
4. 通过生成一个或多个描述要在属性表中显示的控件和调用[BuildDisplayTable](builddisplaytable.md)函数的[DTPAGE](dtpage.md)结构, 或通过实现自定义代码来创建显示表。 
    
5. 调用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)以显示具有已复制属性的属性表。 将指向属性数据对象的指针作为_lpConfigData_参数, 并将指向显示表的指针作为_lpDisplayTable_参数进行传递。 如果要替代此属性表的默认访问模式, 请勿为显示表中表示只读属性的每个控件设置 DT_EDITABLE 标志。 
    
6. 在属性表中进行所有更改后, 调用属性数据对象的**IMAPIProp:: CopyTo**方法将更改后的属性复制回 "配置文件" 部分。 
    
有关显示表的概述, 请参阅[显示表](display-tables.md)。 
  
有关显示表的详细信息, 请参阅[显示表实现](display-table-implementation.md)。 
  
有关实现控件的信息, 请参阅[control Object 实现](control-object-implementation.md)。
  
若要检索用户在 "显示表" 列表框中选择的控件的索引, 请等待用户单击 **"确定" 或 "** **应用**"。 在这种情况下, 所选项的条目标识符被写回到[IMAPIProp: IUnknown](imapipropiunknown.md)接口, 作为[DTBLLBX](dtbllbx.md)结构中**ulPRSetProperty**成员指定的属性的值。 
  
如果您需要能够在列表框中添加或删除项目, 则使用显示表和[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法将不起作用。 相反, 请考虑使用 comdlg32 文件中包含的 Win32 属性表 API 实现属性表。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

