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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406218"
---
# <a name="display-tables"></a>显示表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示表描述如何显示特定类型的对话框，即具有一个或多个专用于显示并可能编辑一个或多个属性的选项卡式属性页的对话框。 与每个显示表相关联的是 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口实现。 **IMAPIProp** 实现维护对话框中显示的属性数据。 
  
显示表中的行代表对话框中显示的控件或用户界面对象。 MAPI 定义许多类型的控件，一些控件具有静态值，有些控件具有用户可更改的动态值。 大多数控件都可以与使用 **IMAPIProp** 实现维护的属性相关联。 当用户更改可修改控件的值时，将更新相应的属性。 
  
服务提供程序实现显示表和 **IMAPIProp** 接口。 创建显示表类似于使用脚本语言编写程序。 服务提供程序可以通过： 
  
- 调用 [BuildDisplayTable](builddisplaytable.md) 函数。 
    
    - 或 -
    
- 包括使用表数据对象（支持 [ITableData ： IUnknown](itabledataiunknown.md) 接口的对象）直接填充显示表的自定义代码。 
    
**BuildDisplayTable** 函数将显示表结构中的信息与对话框资源中的可视元素组合在一起，以生成显示表行。 函数返回一个指向 [IMAPITable ： IUnknown](imapitableiunknown.md) 接口实现的指针，以及指向 **ITableData** 接口实现（如果需要）的指针。 
  
使用 **BuildDisplayTable** 创建显示表非常简单，并且当显示元素更改时，维护将更容易。 但是，喜欢不使用 **BuildDisplayTable** 的服务提供商可以使用使用 **ITableData** 方法的自定义代码创建显示表。 例如，具有属性页的现有模板结构的服务提供商可能希望创建自定义代码，而不是 **使用 BuildDisplayTable**。
  
服务提供商有多种方法可以针对其显示表实现属性接口。 其中包括：
  
- 提供标准 [IMAPIProp ：IUnknown](imapipropiunknown.md) 实现。 
    
- 提供包装 **的 IMAPIProp** 实现，该实现包括执行标准调用之前的特殊处理。 
    
- 提供 [IPropData ：IMAPIProp](ipropdataimapiprop.md) 实现。 
    
实现的类型取决于要显示的数据的特征和负责的服务提供商。 例如，如果两个编辑控件的数据与其中一个控件发生更改时存在隐式关系， **则 IMAPIProp** 实现必须适当地更改另一个控件的值。 
  
显示表的必需列集具有以下属性：
  
|||
|:-----|:-----|
|**PR_XPOS (** [PidTagXCoordinate](pidtagxcoordinate-canonical-property.md))   <br/> |**PR_YPOS (** [PidTagYCoordinate](pidtagycoordinate-canonical-property.md))   <br/> |
|**PR_DELTAX (** [PidTagDeltaX](pidtagdeltax-canonical-property.md))   <br/> |**PR_DELTAY (** [PidTagDeltaY](pidtagdeltay-canonical-property.md))   <br/> |
|**PR_CONTROL_TYPE (** [PidTagControlType)](pidtagcontroltype-canonical-property.md)  <br/> |**PR_CONTROL_FLAGS (** [PidTagControlFlags](pidtagcontrolflags-canonical-property.md))   <br/> |
|**PR_CONTROL_STRUCTURE (** [PidTagControlStructure](pidtagcontrolstructure-canonical-property.md))   <br/> |**PR_CONTROL_ID (** [PidTagControlId)](pidtagcontrolid-canonical-property.md)  <br/> |
   
 **PR_XPOS** 和 **PR_YPOS** 指定控件左上角的 X 和 Y 坐标。 水平单位为对话框基本宽度单位的 1/4;垂直单位为对话框基本高度单位的 1/8。 Windows从当前系统字体的高度和宽度计算当前对话框的基本单位。 坐标相对于属性页区域原点。 属性页的大小限制为大约 200 到 180 个对话框单位。 
  
 **PR_DELTAX** 和 **PR_DELTAY** 控件的宽度和高度。 这些是 ULONG 值。 宽度单位为对话框基本宽度单位的 1/4;高度单位是对话框基本高度单位的 1/8。 坐标相对于控件的原点。 
  
其他四个属性描述了控件的各种特征。 **PR_CONTROL_TYPE** 指示控件的类型。 MAPI 定义 12 种类型的控件，每个控件都有一组不同的属性。 这些属性在 flags 属性中进行了 **描述，PR_CONTROL_FLAGS。** 属性示例包括控件是可编辑还是必需。 
  
控件结构 **PR_CONTROL_STRUCTURE** 包含与特定控件类型有关的信息。 每种类型的控件都使用不同的结构进行描述。 例如，使用 [DTBLEDIT](dtbledit.md) 结构描述编辑控件。 **DTBLEDIT** 结构包含列出可放置在控件上的字符数和特定类型的成员，以及一个属性标记，用于标识其值将显示在控件中的属性。 **PR_CONTROL_STRUCTURE** 存储为二进制属性。 
  
控件标识符 PR_CONTROL_ID **，唯** 一标识显示表所描述的对话框中的控件。 **PR_CONTROL_ID** 从 **BuildDisplayTable** 用于创建显示表的 [DTCTL](dtctl.md)结构的 *lpbNotif* 和 *cbNotif* 成员中设置的值。 由于 MAPI 有时组合显示表，因此PR_CONTROL_ID **标识符应** 始终是唯一的。 通常，提供程序会向用户分配 [GUID](guid.md) **PR_CONTROL_ID** 以确保其唯一性。 当 **PR_CONTROL_ID** 显示表通知时，TABLE_NOTIFICATION属性将 [](table_notification.md)包含在该结构中。 
  
有关显示表的信息，请参阅显示表[实现](display-table-implementation.md)[和关于显示表通知](about-display-table-notifications.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

