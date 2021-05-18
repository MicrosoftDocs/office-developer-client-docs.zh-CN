---
title: IPersistMessageSaveCompleted
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.SaveCompleted
api_type:
- COM
ms.assetid: 83161011-90b4-49cb-9bcd-153a21a10977
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 021be209a2b2c891b668fa401500d6220619f9bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317134"
---
# <a name="ipersistmessagesavecompleted"></a>IPersistMessage::SaveCompleted

**适用于**：Outlook 2013 | Outlook 2016 
  
通知窗体保存操作已完成。 
  
```cpp
HRESULT SaveCompleted(
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a>参数

_pMessage_
  
> [in]指向新保存的邮件的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
E_INVALIDARG 
  
> _pMessage_ 参数为 NULL，并且表单为 [HandsOffFromNormal](handsofffromnormal-state.md)或 [HandsOffAfterSave](handsoffaftersave-state.md)状态。 
    
E_UNEXPECTED 
  
> 表单未在下列状态之一：
    
   - HandsOffFromNormal
    
   - HandsOffAfterSave
    
   - [NoScribble](noscribble-state.md)
    
## <a name="remarks"></a>备注

表单 **查看器调用 IPersistMessage：：SaveCompleted** 方法，以通知表单已保存所有挂起的更改。 只有在表单具有以下状态之一时，才应调用 **SaveCompleted：** 
  
- HandsOffFromNormal
    
- HandsOffAfterSave
    
- NoScribble
    
## <a name="notes-to-implementers"></a>针对实现者的说明

**SaveCompleted** 方法可以执行几种可能的操作，具体取决于邮件指针参数包含哪些内容以及邮件的状态。 但是，当操作成功时，始终保存  _pMessage_ 参数指向的消息的当前状态，并转换窗体到 [其 Normal](normal-state.md) 状态。 
  
下表介绍了影响应在 SaveCompleted 的实现中采取的 **操作的条件**。
  
|**条件**|**操作**|
|:-----|:-----|
|_pMessage 参数_ 为 [NULL，IPersistMessage：：Save](ipersistmessage-save.md)方法的 _fSameAsLoad_ 参数设置为 TRUE。  <br/> |调用 [所有注册查看器的 IMAPIViewAdviseSink：：OnSaved](imapiviewadvisesink-onsaved.md) 方法，将表单标记为干净，并返回S_OK。  <br/> |
|_pMessage 参数_ 为 **NULL，IPersistMessage：：Save** 方法的 _fSameAsLoad_ 参数设置为 FALSE。  <br/> |返回S_OK。  <br/> |
|表单位于 HandsOffFromNormal 状态。  <br/> |释放当前邮件并将其替换为  _pMessage_ 参数指向的消息。 调用替换邮件的 [IUnknown：：AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx) 方法并返回S_OK。  <br/> |
|表单位于 HandsOffAfterSave 状态。  <br/> |调用 **所有注册查看器的 IMAPIViewAdviseSink：：OnSaved** 方法，将表单标记为干净，并返回S_OK。  <br/> |
|表单的状态为[NoScribble。](noscribble-state.md)  <br/> |释放当前邮件并将其替换为  _pMessage_ 指向的消息。 调用替换邮件的 **IUnknown：：AddRef** 方法。 调用 **所有注册查看器的 IMAPIViewAdviseSink：：OnSaved** 方法，将表单标记为干净，并返回S_OK。  <br/> |
|表单为 HandsOff 状态之一  _，pMessage_ 参数设置为 NULL。  <br/> |返回E_INVALIDARG。  <br/> |
|表单的状态不是 HandsOff 状态或 NoScribble 状态之一。  <br/> |返回E_UNEXPECTED。  <br/> |
   
有关保存存储对象的信息，请参阅 [IPersistStorage：：SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) 或 [IPersistFile：：SaveCompleted 方法](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted) 的文档。 
  
## <a name="see-also"></a>另请参阅

- [IPersistMessage : IUnknown](ipersistmessageiunknown.md)
- [表单状态](form-states.md)
