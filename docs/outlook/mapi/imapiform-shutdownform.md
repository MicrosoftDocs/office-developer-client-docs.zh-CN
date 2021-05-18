---
title: IMAPIFormShutdownForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIForm.ShutdownForm
api_type:
- COM
ms.assetid: f1e2a526-40ad-4a93-908f-8ab9a65928a8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 073a76766a296d86e7a23809921b832d494a8f1b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329475"
---
# <a name="imapiformshutdownform"></a>IMAPIForm::ShutdownForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
关闭表单。
  
```cpp
HRESULT ShutdownForm(
  ULONG ulSaveOptions
);
```

## <a name="parameters"></a>参数

 _ulSaveOptions_
  
> [in]一个值，控制在关闭表单之前如何或是否保存表单数据。 可以设置以下标志之一：
    
SAVEOPTS_NOSAVE 
  
> 不应保存表单数据。
    
SAVEOPTS_PROMPTSAVE 
  
> 应提示用户保存表单中任何更改的数据。
    
SAVEOPTS_SAVEIFDIRTY 
  
> 如果表单数据自上次保存后发生了更改，应保存表单数据。 如果未显示用户界面，则表单可以选择切换到使用"打开"选项SAVEOPTS_NOSAVE功能。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单已关闭。
    
E_UNEXPECTED 
  
> 窗体已由之前对 ShutdownForm 的 **调用关闭**。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIForm：：ShutdownForm 方法来** 关闭表单。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在 ShutdownForm 的实现中执行 **以下任务**：
  
1. 检查查看器是否尚未调用 **ShutdownForm，** 如果E_UNEXPECTED返回数据。 虽然这不太可能发生，但您应该检查。
    
2. 调用表单的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) 方法，以便表单和任何内部数据结构的存储保持可用状态，直到处理完成。 
    
3. 确定是否对表单数据有任何未保存的更改。 根据  _ulSaveOptions_ 参数的设置方式，通过调用查看器的 [IMAPIMessageSite：：SaveMessage](imapimessagesite-savemessage.md) 方法保存未保存的数据。 
    
4. 销毁表单的用户界面窗口。
    
5. 通过调用其 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) 方法释放表单的邮件和邮件网站对象。 
    
6. 通过调用其 [IMAPIViewAdviseSink：：OnShutdown](imapiviewadvisesink-onshutdown.md) 方法，通知所有注册的查看者挂起关闭。 
    
7. 调用 [IMAPIViewContext：：SetAdviseSink](imapiviewcontext-setadvisesink.md) 方法，通过将通知接收器指针设置为 null 来取消表单的 **注册以通知**。
    
8. 调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数以释放窗体属性的内存。 
    
9. 调用表单的 **IUnknown：：Release** 方法，与步骤 2 中调用 **的 AddRef** 匹配。 
    
10. 返回S_OK。
    
> [!NOTE]
> 完成这些操作后，表单对象上唯一可以调用的有效方法是 [来自 IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 接口的方法。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当 **ShutdownForm** 返回时，无论它是否返回错误，都通过调用其 **IUnknown：：Release** 方法释放表单。 可以安全地忽略 ShutdownForm 返回 **的任何错误**。
  
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md)
  
[IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md)
  
[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)

