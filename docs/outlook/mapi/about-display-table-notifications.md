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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430012"
---
# <a name="about-display-table-notifications"></a>关于显示表通知

**适用于**：Outlook 2013 | Outlook 2016 
  
显示表上的通知由负责创建显示表的服务提供商发送到 MAPI。 MAPI 通过调用显示表的 [IMAPITable：：Advise](imapitable-advise.md) 方法并指定表修改事件来注册这些通知。 
  
与所有表通知一样，显示表通知包括 [TABLE_NOTIFICATION结构](table_notification.md) 。 只有 **ulTableEvent** 和 **此结构的 propIndex** 成员重要;将忽略其他成员。 **ulTableEvent** 成员设置为 TABLE_ROW_MODIFIED **propIndex** 成员设置为对应行中 **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 列的值。 MAPI 通过调用控件中显示的属性的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法和显示新值来响应通知。 
  
服务提供商可以使用显示表通知协调对话框中相关控件的更改。 例如，如果属性接口实现需要刷新对话框中的一个或多个字段（可能是为了响应在其 **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性中设置了 DT_SET_IMMEDIATE 标志的另一个控件，则它可以生成显示表通知。 显示表通知可以提醒属性接口实现，由于发生了更改或发生外部事件，需要重新读取一个或多个控件的值。 
  
服务提供商可以发出显示表通知，方式为：
  
- 调用 [ITableData：：HrNotify](itabledata-hrnotify.md)，如果显示表是使用表数据对象构建的。
    
    - 或 -
    
- 如果显示表是使用提供程序的 **IMAPITable** 实现构建的，则使用自己的代码。 
    
MAPI 在必要时通过从属性接口实现中重新读取控件的值来响应显示表通知。 下表介绍了 MAPI 如何处理特定类型控件的通知的详细信息。
  
|**Control**|**MAPI 操作**|
|:-----|:-----|
|按钮  <br/> |调用 [IMAPIProp：：OpenProperty，](imapiprop-openproperty.md)以通过 [DTBLBUTTON](dtblbutton.md)结构的 **ulPRControl** 成员所代表的属性来检索控件对象（如果之前调用失败）。 调用控件对象的 [IMAPIControl：：GetState](imapicontrol-getstate.md) 以确定是否应该启用按钮，并相应地启用或禁用按钮。  <br/> |
|复选框  <br/> |重新读取 **ulPRPropertyName 成员** 的值。  <br/> |
|组合框  <br/> |重新打开与 [DTBLCOMBOBOX](dtblcombobox.md)结构的 **ulPRTableName** 成员关联的表。 重新读取所有行，包括 **ulPRPropertyName 成员** 的值。  <br/> |
|下拉列表框  <br/> |重新打开与 [DTBLDDLBX](dtblddlbx.md)结构的 **ulPRTableName** 成员关联的表，然后重新读取所有行。 调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 以检索 **存储在 ulPRDisplayProperty** 和 **ulPRSetProperty 成员中的属性的值** 。  <br/> |
|编辑  <br/> |重新读取属性和重新显示。  <br/> |
|分组框  <br/> |忽略通知。  <br/> |
|标签  <br/> |忽略通知。  <br/> |
|多选列表框  <br/> |如果其中一个列是条目标识符，则刷新列表框。 不会关闭或重新加载相应的对象。  <br/> |
|单选列表框  <br/> |读取 set 属性，尝试标识它。  <br/> |
|多值列表框  <br/> |重新读取属性并重新填充列表框。  <br/> |
|选项卡式页面  <br/> |此控件没有通知;所有内容都是静态的。  <br/> |
|单选按钮  <br/> |重新读取与按钮关联的属性，并存储在 [DTBLRADIOBUTTON](dtblradiobutton.md)结构的 **ulPropTag** 成员中，并借助控件进行相应的选择。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

