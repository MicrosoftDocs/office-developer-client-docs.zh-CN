---
title: 关于显示表通知
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 085151e9-4809-4d2b-ae4d-e318355e1f5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41e6a2c8b6856bf072972325e7e08aabe3e17446
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326409"
---
# <a name="about-display-table-notifications"></a>关于显示表通知

**适用于**：Outlook 2013 | Outlook 2016 
  
显示表上的通知由负责创建显示表到 MAPI 的服务提供程序发送。 这些通知的 MAPI 寄存器, 方法是调用显示表的[IMAPITable:: Advise](imapitable-advise.md)方法并指定表修改事件。 
  
与所有表通知一样, 显示表通知包括[TABLE_NOTIFICATION](table_notification.md)结构。 只有此结构的**ulTableEvent**和**propIndex**成员是非常重要的;其他成员将被忽略。 **ulTableEvent**成员设置为 TABLE_ROW_MODIFIED, **propIndex**成员设置为相应行中**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 列的值。 MAPI 通过调用控件中显示的属性的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 并显示新值, 从而对通知做出响应。 
  
服务提供程序可以使用显示表通知来协调对对话框上的相关控件所做的更改。 例如, 如果属性接口实现需要刷新对话框上的一个或多个字段—可能会响应在其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性中设置了 DT_SET_IMMEDIATE 标志的另一个控件)。它可以生成显示表通知。 显示表通知可警告属性接口实现, 因为有一个或多个控件的值因正在进行更改或发生外部事件而需要重新读取。 
  
服务提供商可以通过以下方式发出显示表通知:
  
- 调用[ITableData:: HrNotify](itabledata-hrnotify.md), 如果显示表是使用 table data 对象生成的。
    
    - 和
    
- 如果显示表是使用提供程序的**IMAPITable**实现生成的, 则使用其自己的代码。 
    
根据需要, MAPI 会根据属性接口实现中的并控件的值来响应显示表通知。 下表介绍了有关 MAPI 如何处理特定类型的控件的通知的详细信息。
  
|**Control**|**MAPI 操作**|
|:-----|:-----|
|按钮  <br/> |调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)通过[DTBLBUTTON](dtblbutton.md)结构的**ulPRControl**成员所表示的属性检索 control 对象 (如果调用以前失败)。 调用 control 对象的[IMAPIControl:: GetState](imapicontrol-getstate.md)以确定是否应启用该按钮, 并相应地启用或禁用该按钮。  <br/> |
|复选框  <br/> |Rereads **ulPRPropertyName**成员的值。  <br/> |
|组合框  <br/> |重新打开与[DTBLCOMBOBOX](dtblcombobox.md)结构的**ulPRTableName**成员相关联的表。 Rereads 所有行, 包括**ulPRPropertyName**成员的值。  <br/> |
|下拉列表框  <br/> |重新打开与[DTBLDDLBX](dtblddlbx.md)结构的**ulPRTableName**成员关联的表, 并 rereads 所有行。 调用[IMAPIProp:: GetProps](imapiprop-getprops.md)检索存储在**ulPRDisplayProperty**和**ulPRSetProperty**成员中的属性的值。  <br/> |
|编辑  <br/> |Rereads 属性并重新所的属性。  <br/> |
|分组框  <br/> |忽略通知。  <br/> |
|标签  <br/> |忽略通知。  <br/> |
|多选列表框  <br/> |如果其中一个列是条目标识符, 则刷新列表框。 相应的对象不会关闭或重新加载。  <br/> |
|单个选择列表框  <br/> |读取 set 属性, 尝试识别该属性。  <br/> |
|多值列表框  <br/> |Rereads 属性并重新填充列表框。  <br/> |
|选项卡页  <br/> |此控件没有通知;一切都是静态的。  <br/> |
|单选按钮  <br/> |Rereads 与按钮关联的属性, 并将其存储在[DTBLRADIOBUTTON](dtblradiobutton.md)结构的**ulPropTag**成员中, 并使用控件进行适当的选择。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

