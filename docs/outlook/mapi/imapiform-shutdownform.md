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
  
> 实时用于控制表单中的数据在窗体关闭之前的保存方式或是否保存的值。 可以设置下列标志之一:
    
SAVEOPTS_NOSAVE 
  
> 不应保存窗体数据。
    
SAVEOPTS_PROMPTSAVE 
  
> 应提示用户在表单中保存任何已更改的数据。
    
SAVEOPTS_SAVEIFDIRTY 
  
> 如果表单数据自上次保存后进行了更改, 则应将其保存。 如果未显示用户界面, 则表单可以选择切换为使用 SAVEOPTS_NOSAVE 选项的功能。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单已关闭。
    
E_UNEXPECTED 
  
> 表单已被以前调用**ShutdownForm**关闭。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIForm:: ShutdownForm**方法以关闭窗体。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

在您的**ShutdownForm**实现中执行以下任务:
  
1. 检查查看器是否尚未调用**ShutdownForm**, 如果有, 则返回 E_UNEXPECTED。 尽管这不太可能, 但应该进行检查。
    
2. 调用表单的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法, 以便在处理完成后, 表单和任何内部数据结构的存储仍可用。 
    
3. 确定表单数据是否有任何未保存的更改。 根据通过调用您的查看器的[IMAPIMessageSite:: SaveMessage](imapimessagesite-savemessage.md)方法设置_ulSaveOptions_参数的方式, 保存未保存的数据。 
    
4. 销毁表单的用户界面窗口。
    
5. 通过调用其[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法来释放表单的邮件和邮件网站对象。 
    
6. 通过调用[IMAPIViewAdviseSink:: OnShutdown](imapiviewadvisesink-onshutdown.md)方法, 通知所有已注册的查看器是否有挂起的关闭。 
    
7. 通过将建议接收器指针设置为**null**, 调用[IMAPIViewContext:: SetAdviseSink](imapiviewcontext-setadvisesink.md)方法以取消表单的注册通知。
    
8. 调用[MAPIFreeBuffer](mapifreebuffer.md)函数以释放窗体属性的内存。 
    
9. 调用表单的**IUnknown:: Release**方法, 匹配在步骤2中进行的**AddRef**呼叫。 
    
10. 返回 S_OK。
    
> [!NOTE]
> 完成这些操作后, 可以调用的窗体对象上唯一有效的方法是[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)接口中的方法。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当**ShutdownForm**返回时, 无论是否返回错误, 都通过调用其**IUnknown:: release**方法来释放窗体。 您可以安全地忽略由**ShutdownForm**返回的任何错误。
  
## <a name="see-also"></a>另请参阅



[IMAPIMessageSite::SaveMessage](imapimessagesite-savemessage.md)
  
[IMAPIViewAdviseSink::OnShutdown](imapiviewadvisesink-onshutdown.md)
  
[IMAPIViewContext::SetAdviseSink](imapiviewcontext-setadvisesink.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPIForm : IUnknown](imapiformiunknown.md)

