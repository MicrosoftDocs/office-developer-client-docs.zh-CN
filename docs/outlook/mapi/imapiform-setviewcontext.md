---
title: IMAPIFormSetViewContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.SetViewContext
api_type:
- COM
ms.assetid: a7b10007-42d8-4755-8362-f8ad9a8dad68
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 81d99b2bbe6ef7914a4b7d253a3472026872260d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350944"
---
# <a name="imapiformsetviewcontext"></a>IMAPIForm::SetViewContext

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
建立窗体的视图上下文。 
  
```cpp
HRESULT SetViewContext(
  LPMAPIVIEWCONTEXT pViewContext
);
```

## <a name="parameters"></a>参数

 _pViewContext_
  
> 实时指向表单的新视图上下文的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功设置了视图上下文。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIForm:: SetViewContext**方法, 以将特定的窗体视图上下文设置为当前。 一个窗体一次只能有一个视图上下文。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

大多数表单服务器通过使用以下算法来实现**SetViewContext** : 
  
- 如果窗体已存在视图上下文, 则通过在_pmnvs_参数中调用[IMAPIViewContext:: SetAdviseSink](imapiviewcontext-setadvisesink.md)方法, 然后调用视图**** 上下文的 IUnknown, 来取消表单的注册[:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来递减其引用计数。 
    
- 如果新的视图上下文不为**null**, 则通过使用_pViewContext_参数设置新的视图建议接收器来调用**IMAPIViewContext:: SetAdviseSink** 。 
    
- 如果新的视图上下文不为**null**, 则调用[IMAPIViewContext:: GetViewStatus](imapiviewcontext-getviewstatus.md)方法以确定已设置的状态标志。 
    
- 如果新的视图上下文不为**null**, 则将其存储并调用其[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法以增加其引用计数。 
    
- 更新依赖于视图上下文的任何用户界面元素。 
    
根据从 IMAPIViewContext 返回的状态标志 **:: GetViewStatus**, **SetViewContext**还可以执行其他操作。 例如, 如果返回 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志, 则**SetViewContext**可以为新的视图上下文启用**下一个**和**上一个**按钮。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions  <br/> |CreateAndDisplayNewMailInFolder  <br/> |MFCMAPI 使用**IMAPIForm:: SetViewContext**方法在窗体显示之前在窗体上设置 MFCMAPI 的视图上下文。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

