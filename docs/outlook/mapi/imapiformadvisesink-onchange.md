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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 02663570e3173bbd696af732e71f060d9dee49bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286626"
---
# <a name="imapiformadvisesinkonchange"></a>IMAPIFormAdviseSink::OnChange

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示表单查看器的状态中发生了更改。 
  
```cpp
HRESULT OnChange(
  ULONG ulDir
);
```

## <a name="parameters"></a>参数

 _ulDir_
  
> 实时标志的位掩码, 提供有关在窗体中的查看器和预期响应中发生的更改的信息。 可以设置以下标志:
    
VCSTATUS_CATEGORY 
  
> 另一个类别中有下一个或上一个邮件。 
    
VCSTATUS_INTERACTIVE 
  
> 表单应显示用户界面。 如果未设置此标志, 则该窗体应禁止显示用户界面, 即使是响应通常会导致显示用户界面的动作也是如此。 
    
VCSTATUS_MODAL 
  
> 窗体是窗体查看器的模式。 
    
VCSTATUS_NEXT 
  
> 表单查看器中有下一封邮件。 
    
VCSTATUS_PREV 
  
> 表单查看器中有上一封邮件。 
    
VCSTATUS_READONLY 
  
> 应禁用删除、提交和移动操作。 
    
VCSTATUS_UNREAD 
  
> 表单查看器中存在下一个或上一个未读邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormAdviseSink:: OnChange**方法来通知表单查看器状态发生的更改。 通常情况下, 唯一的更改是根据查看器中的下一个或上一个邮件是否存在, 设置或清除 VCSTATUS_NEXT 或 VCSTATUS_PREVIOUS 标志。 因此, form 对象将启用或禁用它支持的任何下一个或上一个操作。 
  
VCSTATUS_MODAL 和 VCSTATUS_INTERACTIVE 的设置在视图上下文中创建后无法更改。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

此方法的具体实现完全依赖于窗体的具体实现。 大多数窗体对象使用此方法更改其用户界面 (例如, 启用或禁用菜单命令或按钮以匹配查看器状态标志参数)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md)

