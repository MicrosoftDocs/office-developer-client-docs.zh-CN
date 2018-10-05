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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395054"
---
# <a name="ipersistmessagesavecompleted"></a>IPersistMessage::SaveCompleted

**适用于**：Outlook 2013 | Outlook 2016 
  
通知窗体的保存操作已完成。 
  
```cpp
HRESULT SaveCompleted(
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a>参数

_pMessage_
  
> [in]一个指向新的已保存的邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
E_INVALIDARG 
  
> _PMessage_参数为 NULL，表单中的[HandsOffFromNormal](handsofffromnormal-state.md)或[HandsOffAfterSave](handsoffaftersave-state.md)状态。 
    
E_UNEXPECTED 
  
> 窗体不处于以下状态之一：
    
   - HandsOffFromNormal
    
   - HandsOffAfterSave
    
   - [NoScribble](noscribble-state.md)
    
## <a name="remarks"></a>说明

**IPersistMessage::SaveCompleted**调用表单查看器通知的表单的已保存所有挂起的更改。 仅当表单处于以下状态之一时，应该调用**SaveCompleted** : 
  
- HandsOffFromNormal
    
- HandsOffAfterSave
    
- NoScribble
    
## <a name="notes-to-implementers"></a>针对实现者的说明

有多个可能的操作的**SaveCompleted**方法可执行，具体取决于哪些邮件指针参数包含，以及邮件是什么状态。 但是，操作成功后，始终保存_pMessage_参数指向的消息和转换的当前状态表单到其[正常](normal-state.md)状态。 
  
下表描述了影响的**SaveCompleted**实现中应采取的操作的条件。
  
|**条件**|**操作**|
|:-----|:-----|
|_PMessage_参数为 NULL，并且[IPersistMessage::Save](ipersistmessage-save.md)方法的_fSameAsLoad_参数设置为 TRUE。  <br/> |呼叫所有已注册的查看器的[IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md)方法中，将表单作为干净，并返回 S_OK 标记。  <br/> |
|_PMessage_参数为 NULL，并且**IPersistMessage::Save**方法的_fSameAsLoad_参数设置为 FALSE。  <br/> |返回 S_OK。  <br/> |
|窗体处于 HandsOffFromNormal 状态。  <br/> |将当前的邮件释放，并将它替换_pMessage_参数指向的消息。 调用替换邮件[IUnknown::AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法，并返回 S_OK。  <br/> |
|窗体处于 HandsOffAfterSave 状态。  <br/> |呼叫所有已注册的查看器的**IMAPIViewAdviseSink::OnSaved**方法中，将表单作为干净，并返回 S_OK 标记。  <br/> |
|窗体处于[NoScribble](noscribble-state.md)状态。  <br/> |将当前的邮件释放并将替换所指_pMessage_的邮件。 调用替换邮件**IUnknown::AddRef**方法。 呼叫所有已注册的查看器的**IMAPIViewAdviseSink::OnSaved**方法中，将表单作为干净，并返回 S_OK 标记。  <br/> |
|窗体处于 HandsOff 状态之一，并且_pMessage_参数设置为 NULL。  <br/> |返回 E_INVALIDARG。  <br/> |
|窗体处于以外 HandsOff 状态的状态或 NoScribble 状态。  <br/> |返回 E_UNEXPECTED。  <br/> |
   
有关保存存储对象的详细信息，请参阅[IPersistStorage::SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted)或[IPersistFile::SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted)方法的文档。 
  
## <a name="see-also"></a>另请参阅

- [IPersistMessage : IUnknown](ipersistmessageiunknown.md)
- [表单状态](form-states.md)
