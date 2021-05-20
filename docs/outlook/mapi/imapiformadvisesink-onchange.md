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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431895"
---
# <a name="imapiformadvisesinkonchange"></a>IMAPIFormAdviseSink::OnChange

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示表单查看器的状态发生了更改。 
  
```cpp
HRESULT OnChange(
  ULONG ulDir
);
```

## <a name="parameters"></a>参数

 _ulDir_
  
> [in]标志的位掩码，提供有关查看器中发生的更改和窗体中预期响应的信息。 可以设置以下标志：
    
VCSTATUS_CATEGORY 
  
> 存在另一个类别中的下一封邮件或上一封邮件。 
    
VCSTATUS_INTERACTIVE 
  
> 表单应显示用户界面。 如果未设置此标志，则表单应禁止显示用户界面，即使该动作通常会导致显示用户界面。 
    
VCSTATUS_MODAL 
  
> 窗体对于窗体查看器是模式窗体。 
    
VCSTATUS_NEXT 
  
> 表单查看器中还有下一条消息。 
    
VCSTATUS_PREV 
  
> 表单查看器中之前有一条消息。 
    
VCSTATUS_READONLY 
  
> 应禁用删除、提交和移动操作。 
    
VCSTATUS_UNREAD 
  
> 窗体查看器中出现下一条或上一条未读邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormAdviseSink：：OnChange** 方法来通知表单查看者状态的变化。 通常，唯一的变化是基于查看器中是否存在下一封邮件或上VCSTATUS_NEXT或上一封邮件，设置或清除 VCSTATUS_NEXT 或 VCSTATUS_PREVIOUS 标志。 然后，form 对象将启用或禁用它支持的任何下一个或上一个操作。 
  
创建视图VCSTATUS_MODAL VCSTATUS_INTERACTIVE在视图上下文中无法更改其设置。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

此方法的特定实现完全依赖于表单的具体内容。 大多数表单对象使用此方法来更改其用户界面 (例如，启用或禁用菜单命令或按钮以匹配查看器状态标志参数) 。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::ActivateNext](imapiviewcontext-activatenext.md)
  
[IMAPIFormAdviseSink : IUnknown](imapiformadvisesinkiunknown.md)

