---
title: IMAPIFormAdviseSinkOnChange
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormAdviseSink.OnChange
api_type:
- COM
ms.assetid: d700b40f-e5b2-4d37-bf1f-8fd3dfa0dda5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e32157f41632b782fbacf87e0411c18d167b4279
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576678"
---
# <a name="imapiformadvisesinkonchange"></a>IMAPIFormAdviseSink::OnChange

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示在表单查看器的状态发生更改。 
  
```cpp
HRESULT OnChange(
  ULONG ulDir
);
```

## <a name="parameters"></a>参数

 _ulDir_
  
> [in]位掩码的标志，提供有关在查看器和窗体中的预期的响应中未发生更改的信息。 可以设置以下标志：
    
VCSTATUS_CATEGORY 
  
> 在其他类别没有下一个或上一条消息。 
    
VCSTATUS_INTERACTIVE 
  
> 表单应显示的用户界面。 如果未设置此标志，表单应禁止显示用户界面，即使在响应通常会导致用户界面将显示动词。 
    
VCSTATUS_MODAL 
  
> 窗体是模式窗体查看器。 
    
VCSTATUS_NEXT 
  
> 在窗体查看器没有下一条消息。 
    
VCSTATUS_PREV 
  
> 在窗体查看器没有上一条消息。 
    
VCSTATUS_READONLY 
  
> 删除、 提交，和移动操作应被禁用。 
    
VCSTATUS_UNREAD 
  
> 在窗体查看器没有下一页或上一页未读的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIFormAdviseSink::OnChange**方法以通知有关查看器的状态更改窗体。 通常，更改只是设置或清除基于存在查看器中的下一页或上一页邮件 VCSTATUS_NEXT 或 VCSTATUS_PREVIOUS 标志。 因此，form 对象然后启用或禁用它支持的任何下一个或上一操作。 
  
创建它之后，VCSTATUS_MODAL 和 VCSTATUS_INTERACTIVE 的设置不能更改了视图上下文中。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

具体的实现此方法是完全取决于该窗体的具体信息。 大多数窗体对象使用此方法来更改其用户界面 （例如，若要启用或禁用菜单命令或按钮来查看器的状态标志参数匹配）。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md)

