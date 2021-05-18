---
title: 控制对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ad62ff0-c527-4e75-a2af-b5906a7588e8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8304021565638f8a5893d0be8cd6a94ed62a8d95
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422605"
---
# <a name="control-object-implementation"></a>控制对象实现

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
控制对象或支持 [IMAPIControl ： IUnknown](imapicontroliunknown.md) 接口的对象由提供程序实现，以向出现在 MAPI 对话框中的按钮添加功能。 只能为按钮实现 Control 对象。 
  
 **IMAPIControl** 有三种方法 [：GetLastError、GetState](imapicontrol-getlasterror.md)和 [Activate](imapicontrol-activate.md)。 [](imapicontrol-getstate.md) 
  
MAPI 调用 **GetState** 以确定是否禁用按钮。 在下列情况下调用 **GetState：** 
  
- 第一次显示显示按钮的对话框时。
    
- 为按钮发出显示表通知时。 
    
将  _lpulState_ 参数的内容设置为 MAPI_DISABLED如果用户无法与按钮交互，MAPI_ENABLED用户是否可交互。 
  
当用户单击该按钮时，MAPI 调用 **Activate**。 **Activate** 执行已与按钮关联的任务。 此任务可以是适用于提供程序的任何内容，例如显示对话框或更新属性。 如果任务由于用户取消而失败，则返回MAPI_E_USER_CANCEL。 对于其他失败原因，请返回相应的错误值。 
  
如果任务成功且链接到对话框上另一个控件中反映的属性更改，请调用 [ITableData：：HrNotify](itabledata-hrnotify.md)。 **调用 HrNotify** 以使用已更改属性的 **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性发出显示表通知 [TABLE_NOTIFICATION结构。](table_notification.md) 不要将新属性值放在结构中;相反，在调用 [IMAPIProp：：GetProps 时](imapiprop-getprops.md) 返回它。 尽管显示表通知通常不能用于禁用或启用控件，但它可以与按钮一起使用。 MAPI 将刷新更改的控件以响应通知。 
  
当 Activate 返回错误时，MAPI 将调用控件 **的 GetLastError** 方法，而不是MAPI_E_USER_CANCEL。 如果 **GetLastError** 在 [MAPIERROR](mapierror.md) 结构中将扩展的错误信息显示在  _lppMAPIError_ 参数的内容中，则 MAPI 会为用户显示此信息。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

