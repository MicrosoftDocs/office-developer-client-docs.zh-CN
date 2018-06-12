---
title: 属性表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f3475206-0237-4b5b-8efd-abd5d5e0b6c3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 406451adac3cd73286feb787bd6b4d2f356aa283
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778571"
---
# <a name="property-sheet-implementation"></a>属性表实现

  
  
**适用于**： Outlook 
  
属性表是一个用于显示对象的属性对话框。 属性可以为只读，使用户仅可以查看它们或读/写，使用户可以进行更改。 属性表包含一个或多个调用页面的重叠子窗口。 每个页面包含用于设置一组相关的属性的控件窗口。 用户通过选择将相应的网页提到的前景色的属性表选项卡导航页面之间。
  
服务提供商必须实现的属性表显示最小集与邮件服务中配置相关的属性。 如果您允许要更改这些消息服务属性，您也可以允许用户的客户端应用程序，如控制面板，以进行更改，或以编程方式实现所做的更改。 实现属性表以显示和编辑其他类型的属性是可选的。 
  
通常情况下，您需要在下列情况下显示属性表：
  
- 当客户端调用状态对象的[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法。 
    
- 当 MAPI 调用提供商对象的登录方法。
    
- 当 MAPI 提供程序的消息服务调用入口点函数。
    
传输提供程序还实现属性表以显示与邮件选项相关的属性和通讯簿提供程序实现的属性页来查看和编辑邮件用户和通讯组列表、 高级搜索的详细的信息条件，然后输入新用户的模板。
  
您可以使用以下三种方法之一创建属性表：
  
- 手动，就像任何对话框。
    
- 使用 Windows SDK 中提供的属性表常见控件。
    
- 通过使用 MAPI 显示表。
    
提供程序应选择最后一个选项 （通过使用显示表创建属性表）。 这是最简单的选项，因为它不需要使用 Windows 用户界面。 
  
若要实现构建您的消息服务属性显示表中的属性表，请使用以下过程：
  
1. 调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)在当前配置文件中打开一节。 传递您[MAPIUID](mapiuid.md)或 NULL，以打开您的提供商的配置文件部分。 
    
2. 调用[CreateIProp](createiprop.md)可创建的属性数据对象。 
    
3. 调用配置文件部分的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法以将所有节的属性复制到的属性数据对象。 
    
4. 创建显示表来构建一个或多个[DTPAGE](dtpage.md)结构描述的控件以显示在属性表和调用[BuildDisplayTable](builddisplaytable.md)函数，或通过实现自定义代码。 
    
5. 调用[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)显示属性表已复制的属性。 将指针传递给为_lpConfigData_参数和一个指向作为_lpDisplayTable_参数显示表的属性数据对象。 如果您想要替代此属性表的默认访问模式，不要中显示表值，该值代表只读属性设置为每个控件的 DT_EDITABLE 标志。 
    
6. 未在属性表中进行的所有更改时, 调用的属性数据对象**IMAPIProp::CopyTo**方法复制更改的属性返回到配置文件部分。 
    
显示表的概述，请参阅[显示表](display-tables.md)。 
  
有关显示表的详细信息，请参阅[显示表实现](display-table-implementation.md)。 
  
有关实现控件的信息，请参阅[控件对象实现](control-object-implementation.md)。
  
若要检索的控件的用户显示表列表框中选择的索引，等待用户单击**确定**或**应用**。 此时，选定项目的项标识符返回写入到[IMAPIProp: IUnknown](imapipropiunknown.md)作为**ulPRSetProperty**成员[DTBLLBX](dtbllbx.md)结构中由指定的属性的值的接口。 
  
如果您需要能够添加或删除项目从列表框，请使用显示表和[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法不起作用。 相反，请考虑实现与 Win32 属性表 API comdlg32.dll 文件中包含的属性表。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

