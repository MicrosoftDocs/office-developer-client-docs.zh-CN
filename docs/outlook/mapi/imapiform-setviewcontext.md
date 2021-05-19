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
  
建立表单的视图上下文。 
  
```cpp
HRESULT SetViewContext(
  LPMAPIVIEWCONTEXT pViewContext
);
```

## <a name="parameters"></a>参数

 _pViewContext_
  
> [in]指向表单的新视图上下文的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置视图上下文。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIForm：：SetViewContext** 方法以将特定的表单视图上下文建立为当前上下文。 表单一次只能有一个视图上下文。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

大多数表单服务器通过以下算法实现 **SetViewContext：** 
  
- 如果表单已存在视图上下文，则通过调用 _pmnvs_ 参数中为 **null** 的 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md)方法取消表单的注册，然后调用视图上下文的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来缩小其引用计数。 
    
- 如果新视图上下文不 **为空**，则使用 _pViewContext_ 参数设置新视图建议接收器来调用 **IMAPIViewContext：：SetAdviseSink。** 
    
- 如果新视图上下文不 **为空**，请调用 [IMAPIViewContext：：GetViewStatus](imapiviewcontext-getviewstatus.md) 方法以确定已设置的状态标志。 
    
- 如果新视图上下文不 **为空**，请存储它并调用其 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 方法来增加其引用计数。 
    
- 更新依赖于视图上下文的任何用户界面元素。 
    
根据从 **IMAPIViewContext：：GetViewStatus** 返回的状态标志 **，SetViewContext** 还可以执行其他操作。 例如，如果返回 VCSTATUS_NEXT 和 VCSTATUS_PREV 标志，**则 SetViewContext** 可以启用新视图上下文的"下一步"和"上一步"按钮。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFormFunctions.cpp  <br/> |CreateAndDisplayNewMailInFolder  <br/> |MFCMAPI 在显示表单之前，使用 **IMAPIForm：：SetViewContext** 方法在表单上设置 MFCMAPI 的视图上下文。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIViewContext::GetViewStatus](imapiviewcontext-getviewstatus.md)
  
[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

