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
ms.openlocfilehash: 26ca126603ac1e695bd14a10cd8d9e637382b2e9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584301"
---
# <a name="imapiformsetviewcontext"></a>IMAPIForm::SetViewContext

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
建立窗体视图上下文。 
  
```cpp
HRESULT SetViewContext(
  LPMAPIVIEWCONTEXT pViewContext
);
```

## <a name="parameters"></a>参数

 _pViewContext_
  
> [in]指向新窗体视图上下文的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置视图上下文。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIForm::SetViewContext**方法为当前建立了特定窗体视图上下文。 窗体可以一次只有一个视图上下文。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

大多数窗体服务器通过使用下面的算法来实现**SetViewContext** : 
  
- 如果表单已经存在了视图上下文，通过在_pmnvs_参数中，调用与**null** [IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法取消窗体的注册，然后调用视图上下文， [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)要引用计数递减方法。 
    
- 如果不**为 null**的新视图上下文，通过使用_pViewContext_参数设置一个新视图的呼叫**IMAPIViewContext::SetAdviseSink**建议接收器。 
    
- 如果不**为 null**的新视图上下文，调用[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)方法来确定已设置的状态标志。 
    
- 如果不**为 null**的新视图上下文，将其存储，并调用其[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法，以增加引用计数。 
    
- 更新依赖于视图上下文的任何用户界面元素。 
    
根据从**IMAPIViewContext::GetViewStatus**返回的状态标志， **SetViewContext**还可以执行其他操作。 例如，如果返回 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志， **SetViewContext**可以启用新的视图上下文**下一步**和**上一页**按钮。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |CreateAndDisplayNewMailInFolder  <br/> |MFCMAPI 使用**IMAPIForm::SetViewContext**方法在窗体上设置 MFCMAPI 的视图上下文，在显示窗体前。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

