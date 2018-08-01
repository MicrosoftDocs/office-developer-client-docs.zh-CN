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
ms.openlocfilehash: 556d7551f64e075d1f15a945ddb1409c3b5a775f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774835"
---
# <a name="display-tables"></a>显示表

  
  
**适用于**： Outlook 
  
显示表介绍了如何显示的对话框中的特定类型 — 一个具有专用于显示和可能编辑一个或多个属性的一个或多个选项卡式的属性页。 关联与每个显示表是[IMAPIProp: IUnknown](imapipropiunknown.md)接口实现。 **IMAPIProp**实现维护对话框中显示的属性数据。 
  
显示表中的行表示的控件或在对话框中显示的用户界面对象。 MAPI 定义许多类型的控件、 一些使用静态值和一些与动态的用户可以更改的值。 大多数控件都可以与维护**IMAPIProp**实现与属性关联。 当用户更改可修改的控件的值时，将更新的相应属性。 
  
服务提供商实现显示表和**IMAPIProp**接口。 创建显示表是类似于编写脚本语言的程序。 服务提供商可以创建由一个显示表： 
  
- 调用[BuildDisplayTable](builddisplaytable.md)函数。 
    
    - 或者-
    
- 包括填充显示表直接使用表数据对象的自定义代码 — 支持的对象， [ITableData: IUnknown](itabledataiunknown.md)接口。 
    
**BuildDisplayTable**函数与从对话框资源来构建显示表格行的可视元素结合使用从显示表结构的信息。 此函数返回一个指向[IMAPITable: IUnknown](imapitableiunknown.md)接口实现，并且，如果请求，指向**ITableData**接口实现的指针。 
  
使用**BuildDisplayTable**创建显示表非常简单，并使维护 visual 元素的显示更改时更轻松。 但是，不想使用**BuildDisplayTable**的服务提供商可以使用的**ITableData**方法的自定义代码创建显示表。 例如，其属性页的现有模板结构服务提供商可能想要创建自定义代码，而不是使用**BuildDisplayTable**。
  
有多种方式服务提供商可以实现其显示表属性接口。 这些工具包括：
  
- 提供一种标准[IMAPIProp: IUnknown](imapipropiunknown.md)实现。 
    
- 提供包括特殊处理之前进行标准调用的换行的**IMAPIProp**实现。 
    
- 提供[IPropData: IMAPIProp](ipropdataimapiprop.md)实现。 
    
实现类型取决于要显示的数据的特征和负责服务提供商。 例如，如果两个编辑控件中的数据之间存在隐式关系，并且其中一个控件更改， **IMAPIProp**实现必须适当地更改其他控件的值。 
  
显示表中其所需的列集具有以下属性：
  
|||
|:-----|:-----|
|**PR_XPOS**([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md))  <br/> |**PR_YPOS**([PidTagYCoordinate](pidtagycoordinate-canonical-property.md))  <br/> |
|**PR_DELTAX**([PidTagDeltaX](pidtagdeltax-canonical-property.md))  <br/> |**PR_DELTAY**([PidTagDeltaY](pidtagdeltay-canonical-property.md))  <br/> |
|**PR_CONTROL_TYPE**([PidTagControlType](pidtagcontroltype-canonical-property.md))  <br/> |**PR_CONTROL_FLAGS**([PidTagControlFlags](pidtagcontrolflags-canonical-property.md))  <br/> |
|**PR_CONTROL_STRUCTURE**([PidTagControlStructure](pidtagcontrolstructure-canonical-property.md))  <br/> |**PR_CONTROL_ID**([PidTagControlId](pidtagcontrolid-canonical-property.md))  <br/> |
   
 **PR_XPOS**和**PR_YPOS**指定控件的左上角的 X 和 Y 坐标。 水平单位属于的对话框基宽度单元; 1/4垂直单位是 1/8 对话框基高度单位。 Windows 计算中的高度和宽度当前的系统字体的当前对话框基本单位。 坐标是相对于原点的属性页区域。 属性页面的大小被限制为大约 200 通过 180 对话框单位。 
  
 **PR_DELTAX**和**PR_DELTAY**是宽度和高度控件。 这些是 ULONG 值。 宽度单位属于的对话框基宽度单元; 1/4高度单位是 1/8 对话框基高度单位。 坐标是相对于控件的原点而言的。 
  
其他四个属性描述控件的各种特征。 **PR_CONTROL_TYPE**指示控件的类型。 MAPI 定义十二个类型的控件，每个都有一组不同的属性。 Flags 属性， **PR_CONTROL_FLAGS**中描述了这些属性。 属性的示例包括控件可编辑或必需。 
  
控制结构， **PR_CONTROL_STRUCTURE**，包含与相关的控件的特定类型的信息。 具有不同结构介绍了每种类型的控件。 例如，与[DTBLEDIT](dtbledit.md)结构描述了编辑控件。 **DTBLEDIT**结构包含成员的数量和特定种可以放在控件和一个用于标识该属性的属性标记其值的字符是控件中显示该列表。 **PR_CONTROL_STRUCTURE**存储为二进制属性。 
  
控件标识符， **PR_CONTROL_ID**，唯一地标识描述显示表对话框中的控件。 **PR_CONTROL_ID**设置从放在*lpbNotif*和*cbNotif*结构的成员的[DTCTL](dtctl.md) **BuildDisplayTable**用于创建显示表中的值。 MAPI 有时合并显示的表，因为**PR_CONTROL_ID**中的标识符应始终是唯一的。 通常情况下，提供程序将[GUID](guid.md)结构分配**PR_CONTROL_ID**以确保其唯一性。 生成显示表通知时，将[TABLE_NOTIFICATION](table_notification.md)结构中包含的**PR_CONTROL_ID**属性。 
  
有关显示表的详细信息，请参阅[显示表实现](display-table-implementation.md)和[有关显示表通知](about-display-table-notifications.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

