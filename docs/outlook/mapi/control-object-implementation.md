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
  
控制对象或支持[IMAPIControl: IUnknown](imapicontroliunknown.md)接口的对象由提供程序实现, 以向出现在 MAPI 对话框中的按钮添加功能。 只能对按钮实现控制对象。 
  
 **IMAPIControl**具有三种方法: [GetLastError](imapicontrol-getlasterror.md)、 [GetState](imapicontrol-getstate.md)和[Activate](imapicontrol-activate.md)。 
  
MAPI 调用**GetState**以确定是否禁用该按钮。 在下列情况下, 将调用**GetState** : 
  
- 第一次显示按钮出现的对话框时。
    
- 为按钮发出显示表通知时。 
    
将_lpulState_参数的内容设置为 MAPI_DISABLED 如果用户无法与按钮和 MAPI_ENABLED 交互 (如果用户可以交互)。 
  
当用户单击此按钮时, MAPI 调用将**激活**。 **激活**: 执行已与按钮相关联的任务。 此任务可以是适合您的提供程序的任何内容, 如显示对话框或更新属性。 如果该任务因用户取消而失败, 则返回 MAPI_E_USER_CANCEL。 对于失败的其他原因, 请返回相应的错误值。 
  
如果任务成功, 并且它链接到的属性更改反映在对话框中的另一个控件中, 则调用[ITableData:: HrNotify](itabledata-hrnotify.md)。 调用**HrNotify**时, 将发出显示表通知, 其中包含更改后的属性的**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性在[TABLE_NOTIFICATION](table_notification.md)结构中。 不要在结构中放置新的属性值;而是在调用[IMAPIProp:: GetProps](imapiprop-getprops.md)时返回它。 尽管通常显示表通知不能用于禁用或启用控件, 但它可以与按钮一起使用。 MAPI 将刷新更改的控件以响应通知。 
  
当**激活**返回除 MAPI_E_USER_CANCEL 之外的错误时, MAPI 会调用控件的**GetLastError**方法。 如果**GetLastError**将扩展的错误信息放在[MAPIERROR](mapierror.md)结构中, 并在_lppMAPIError_参数的内容中返回, 则 MAPI 将为用户显示该信息。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

