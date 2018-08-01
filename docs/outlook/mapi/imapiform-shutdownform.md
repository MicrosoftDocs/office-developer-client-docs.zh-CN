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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9a6ab96a70bce622f44de6576e7b77861302de4f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775374"
---
# <a name="imapiformshutdownform"></a>IMAPIForm::ShutdownForm

  
  
**适用于**： Outlook 
  
关闭表单。
  
```cpp
HRESULT ShutdownForm(
  ULONG ulSaveOptions
);
```

## <a name="parameters"></a>参数

 _ulSaveOptions_
  
> [in]一个控件之前关闭窗体如何或是否保存表单中的数据的值。 可以设置以下标志之一：
    
SAVEOPTS_NOSAVE 
  
> 应不会保存表单数据。
    
SAVEOPTS_PROMPTSAVE 
  
> 应提示用户保存表单中的任何更改的数据。
    
SAVEOPTS_SAVEIFDIRTY 
  
> 如果上次保存后进行了更改，则应保存表单数据。 如果显示没有用户界面时，窗体可以 （可选） 切换到使用 SAVEOPTS_NOSAVE 选项的功能。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 关闭窗体。
    
E_UNEXPECTED 
  
> 以前调用**ShutdownForm**已被关闭窗体。
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIForm::ShutdownForm**方法关闭窗体。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

**ShutdownForm**在实现中执行以下任务：
  
1. 检查的一个查看器不已调用**ShutdownForm**，并返回 E_UNEXPECTED，如果它具有。 尽管这是不可能，应检查。
    
2. 调用窗体的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法，以便完成处理之前，仍可存储窗体和任何内部数据结构。 
    
3. 确定是否有任何未保存的更改窗体的数据。 保存未保存的数据，根据如何_ulSaveOptions_参数设置通过调用查看器的[IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md)方法。 
    
4. 销毁窗体的用户界面窗口。
    
5. 通过调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx)方法释放窗体的邮件和消息网站对象。 
    
6. 通过调用其[IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md)方法通知所有已注册查看器的挂起关闭。 
    
7. 调用[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)方法取消由 advise 接收器指针设置为**null**的通知的窗体的注册。
    
8. 调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放内存的窗体的属性。 
    
9. 调用匹配**AddRef**呼叫在步骤 2 中所做的窗体的**IUnknown::Release**方法。 
    
10. 返回 S_OK。
    
> [!NOTE]
> 这些操作完成后，可能会调用的窗体对象上的唯一有效方法是从[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)接口。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当**ShutdownForm**返回，而不管是否返回错误，通过调用其**IUnknown::Release**方法释放窗体。 您可以忽略**ShutdownForm**返回任何错误。
  
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md)
  
[IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md)
  
[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)

