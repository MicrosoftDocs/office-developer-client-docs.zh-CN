---
title: 控制对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ad62ff0-c527-4e75-a2af-b5906a7588e8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b4b225f7e048ef40a79c4b258629cb01b79368d7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565828"
---
# <a name="control-object-implementation"></a>控制对象实现

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
控制或对象支持的对象， [IMAPIControl: IUnknown](imapicontroliunknown.md)接口，由提供商能够将功能添加到一个 MAPI 对话框中显示的按钮。 只能为按钮实现控件对象。 
  
 **IMAPIControl**具有三个方法： [GetLastError](imapicontrol-getlasterror.md)、 [GetState](imapicontrol-getstate.md)和[激活](imapicontrol-activate.md)。 
  
MAPI 调用**GetState**以确定禁用按钮。 在下列情况下调用**GetState** : 
  
- 当首次显示显示按钮对话框。
    
- 当显示表通知颁发的按钮。 
    
设置为 MAPI_DISABLED _lpulState_参数的内容，如果用户不能与按钮和 MAPI_ENABLED 交互，如果用户可以进行交互。 
  
当用户单击按钮时，MAPI 调用**激活**。 **激活**执行的任务的已与按钮关联。 此任务可以是任何适用于您的提供程序，如显示一个对话框，或更新属性。 如果由于用户取消其任务失败，则返回 MAPI_E_USER_CANCEL。 有关故障其他原因，返回相应的错误值。 
  
如果任务是成功，并且它链接到反映对话框上的另一个控件中的属性更改，则调用[ITableData::HrNotify](itabledata-hrnotify.md)。 **HrNotify**称为发出[TABLE_NOTIFICATION](table_notification.md)结构中的已更改的属性**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性包含的显示表通知。 在结构; 不放置新的属性值相反，它返回时调用[IMAPIProp::GetProps](imapiprop-getprops.md) 。 尽管通常显示表通知不能用于禁用或启用的控件，它可与一个按钮。 MAPI 将刷新更改控件以响应通知。 
  
当**激活**返回之外 MAPI_E_USER_CANCEL 错误，MAPI 调用控件的**GetLastError**方法。 如果**GetLastError**放入它返回_lppMAPIError_参数的内容中的[MAPIERROR](mapierror.md)结构中的扩展的错误信息，MAPI 将显示该用户。 
  
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

