---
title: 显示表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c314ff6d-3e60-4b81-87ac-6ca6753ff633
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b94b0ea69237be3675e1ea02fc3e2bfac337025
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338554"
---
# <a name="display-tables"></a>显示表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示表介绍如何显示特定类型的对话框, 其中一个或多个选项卡式属性页专用于显示且可能编辑一个或多个属性。 与每个显示表相关的是[IMAPIProp: IUnknown](imapipropiunknown.md)接口实现。 **IMAPIProp**实现维护对话框中显示的属性数据。 
  
显示表中的行表示在对话框中显示的控件或用户界面对象。 MAPI 定义了许多类型的控件, 有些控件使用静态值, 而有些则是用户可以更改的动态值。 大多数控件都可以与**IMAPIProp**实现所维护的属性相关联。 当用户更改了可修改控件的值时, 相应的属性也会更新。 
  
服务提供程序实现显示表和**IMAPIProp**接口。 创建显示表类似于编写带有脚本语言的程序。 服务提供商可以通过以下方式创建显示表: 
  
- 调用[BuildDisplayTable](builddisplaytable.md)函数。 
    
    - 和
    
- 包括支持[ITableData: IUnknown](itabledataiunknown.md)接口的对象, 用于直接使用表数据对象填充显示表的自定义代码。 
    
**BuildDisplayTable**函数将显示表结构中的信息与对话框资源中的可视元素组合在一起, 以生成显示表行。 函数返回指向[IMAPITable: IUnknown](imapitableiunknown.md)接口实现的指针, 如果请求, 则返回指向**ITableData**接口实现的指针。 
  
使用**BuildDisplayTable**创建显示表非常简单, 并且在显示可视元素时便于维护。 但是, 不愿使用**BuildDisplayTable**的服务提供程序可以使用自定义代码创建显示表, 该自定义代码使用**ITableData**的方法。 例如, 具有其属性页的现有模板结构的服务提供商可能想要创建自定义代码, 而不是使用**BuildDisplayTable**。
  
服务提供程序可以通过多种方式为其显示表实现属性接口。 具体包括：
  
- 提供标准的[IMAPIProp: IUnknown](imapipropiunknown.md)实现。 
    
- 提供包装的**IMAPIProp**实现, 其中包括在进行标准调用之前进行的特殊处理。 
    
- 提供[IPropData: IMAPIProp](ipropdataimapiprop.md)实现。 
    
实现类型取决于要显示的数据的特征和负责的服务提供商。 例如, 如果两个编辑控件中的数据之间存在隐式关系, 其中一个控件发生了更改, 则**IMAPIProp**实现必须相应地更改另一个控件的值。 
  
显示表在其必需的列集中具有以下属性:
  
|||
|:-----|:-----|
|**PR_XPOS**([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md))  <br/> |**PR_YPOS**([PidTagYCoordinate](pidtagycoordinate-canonical-property.md))  <br/> |
|**PR_DELTAX**([PidTagDeltaX](pidtagdeltax-canonical-property.md))  <br/> |**PR_DELTAY**([PidTagDeltaY](pidtagdeltay-canonical-property.md))  <br/> |
|**PR_CONTROL_TYPE**([PidTagControlType](pidtagcontroltype-canonical-property.md))  <br/> |**PR_CONTROL_FLAGS**([PidTagControlFlags](pidtagcontrolflags-canonical-property.md))  <br/> |
|**PR_CONTROL_STRUCTURE**([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md))  <br/> |**PR_CONTROL_ID**([PidTagControlId](pidtagcontrolid-canonical-property.md))  <br/> |
   
 **PR_XPOS**和**PR_YPOS**指定控件左上角的 X 和 Y 坐标。 水平单位为对话框基本宽度单位的 1/4;垂直单位为对话框基本高度单位的1/8。 Windows 将根据当前系统字体的高度和宽度计算当前的对话框基本单位。 坐标相对于属性页区域的原点。 属性页的大小限制为约 200 x 180 个对话框单元。 
  
 **PR_DELTAX**和**PR_DELTAY**是控件的宽度和高度。 这些值是 ULONG 值。 宽度单位为对话框基本宽度单位的 1/4;高度单位为对话框基本高度单位的1/8。 坐标相对于控件的原点。 
  
其他四个属性描述控件的各种特征。 **PR_CONTROL_TYPE**指示控件的类型。 MAPI 定义了十二种类型的控件, 每种类型都有一组不同的属性。 这些属性在 flags 属性**PR_CONTROL_FLAGS**中进行了说明。 属性的示例包括控件是否可编辑或是否必需。 
  
控制结构**PR_CONTROL_STRUCTURE**包含与特定类型的控件相关的信息。 每种类型的控件都以不同的结构进行描述。 例如, 使用[DTBLEDIT](dtbledit.md)结构对编辑控件进行了描述。 **DTBLEDIT**结构包含的成员列出可以在控件上放置的特定类型的字符数以及用于标识其值将在控件中显示的属性的属性标记。 **PR_CONTROL_STRUCTURE**存储为二进制属性。 
  
控件标识符 ( **PR_CONTROL_ID**) 唯一标识显示表所描述的对话框中的控件。 **PR_CONTROL_ID**是从[DTCTL](dtctl.md)结构的*lpbNotif*和*cbNotif*成员中的值设置的, 由**BuildDisplayTable**用来创建显示表的值。 由于 MAPI 有时会组合显示表, 因此**PR_CONTROL_ID**中的标识符应始终是唯一的。 通常, 提供程序将[GUID](guid.md)结构分配给**PR_CONTROL_ID** , 以确保其唯一性。 当生成显示表通知时, **PR_CONTROL_ID**属性包含在[TABLE_NOTIFICATION](table_notification.md)结构中。 
  
有关显示表的详细信息, 请参阅[显示表实现](display-table-implementation.md)和[关于显示表通知](about-display-table-notifications.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

