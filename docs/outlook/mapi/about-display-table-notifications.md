---
title: 有关显示表通知
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 085151e9-4809-4d2b-ae4d-e318355e1f5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a696357c97a85442bbfd5532892c06d570f6367c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774468"
---
# <a name="about-display-table-notifications"></a>有关显示表通知

**适用于**： Outlook 
  
显示表上的通知发送负责创建显示表为 MAPI 服务提供商。 MAPI 注册这些通知通过调用显示表的[IMAPITable::Advise](imapitable-advise.md)方法，并指定已修改的表的事件。 
  
与所有表通知，显示表通知包括[TABLE_NOTIFICATION](table_notification.md)结构。 仅**ulTableEvent**和此结构的**propIndex**成员非常巨大;其他成员将被忽略。 **UlTableEvent**成员设置为 TABLE_ROW_MODIFIED 并且**propIndex**成员设置为**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 列中的相应行中的值。 MAPI 响应的通知，通过调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法控件中显示的属性和显示新值。 
  
显示表通知可以由服务提供商，用于协调对对话框上的相关控件的更改。 例如，如果该属性接口实现需要刷新对话框上的一个或多个字段 — 到已将 DT_SET_IMMEDIATE 标志设置其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性中的另一个控件的响应中或许 —它可以生成显示表通知。 显示表通知可以警报的一个或多个控件的值必须由于正在所做的更改重新读取该属性接口实现或外部事件发生。 
  
服务提供商可以发出通过显示表通知：
  
- 如果显示表生成与 table 数据对象，调用[ITableData::HrNotify](itabledata-hrnotify.md)。
    
    - 或者-
    
- 如果提供程序的**IMAPITable**实现构建显示表，则使用其自己的代码。 
    
MAPI 响应通过来显示表通知在必要时重新读取从属性接口实现的控件的值。 下表介绍周围 MAPI 如何处理特定类型的控件的通知的详细信息。
  
|**控件**|**MAPI 操作**|
|:-----|:-----|
|按钮  <br/> |调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)检索通过呼叫具有失败以前由[DTBLBUTTON](dtblbutton.md)结构的**ulPRControl**成员属性的控件对象。 呼叫控件对象的[IMAPIControl::GetState](imapicontrol-getstate.md)来确定按钮应启用和启用或禁用相应的按钮。  <br/> |
|复选框  <br/> |重新值读取**ulPRPropertyName**成员。  <br/> |
|组合框  <br/> |重新打开与[DTBLCOMBOBOX](dtblcombobox.md)结构的**ulPRTableName**成员关联的表。 重新读取的所有行包括**ulPRPropertyName**成员值。  <br/> |
|下拉列表框  <br/> |重新打开与[DTBLDDLBX](dtblddlbx.md)结构的**ulPRTableName**成员关联的表和重新读取的所有行。 调用[IMAPIProp::GetProps](imapiprop-getprops.md)检索**ulPRDisplayProperty**和**ulPRSetProperty**成员中存储的属性的值。  <br/> |
|编辑  <br/> |重新读取属性并重新显示。  <br/> |
|分组框  <br/> |忽略通知。  <br/> |
|标签  <br/> |忽略通知。  <br/> |
|多选列表框  <br/> |如果其中一列的项标识符，刷新列表框。 相应的对象不是关闭或重新加载。  <br/> |
|单一选择列表框  <br/> |读取设置属性，尝试识别它。  <br/> |
|多值的列表框  <br/> |重新读取属性和重新填充列表框。  <br/> |
|选项卡式的页面  <br/> |有此控件，则不通知所有内容是静态的。  <br/> |
|单选按钮  <br/> |重新读取与按钮关联的属性和存储在[DTBLRADIOBUTTON](dtblradiobutton.md)结构的**ulPropTag**成员使控件具有适当的选择。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

