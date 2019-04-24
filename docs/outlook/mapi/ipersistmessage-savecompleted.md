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
  
通知表单保存操作已完成。 
  
```cpp
HRESULT SaveCompleted(
  LPMESSAGE pMessage
);
```

## <a name="parameters"></a>参数

_pMessage_
  
> 实时指向新保存的邮件的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
E_INVALIDARG 
  
> _pMessage_参数为 NULL, 该窗体处于[HandsOffFromNormal](handsofffromnormal-state.md)或[HandsOffAfterSave](handsoffaftersave-state.md)状态。 
    
E_UNEXPECTED 
  
> 表单不处于以下状态之一:
    
   - HandsOffFromNormal
    
   - HandsOffAfterSave
    
   - [NoScribble](noscribble-state.md)
    
## <a name="remarks"></a>注解

表单查看器调用**IPersistMessage:: SaveCompleted**方法, 以通知表单已保存所有挂起的更改。 仅当窗体处于以下状态之一时, 才应调用**SaveCompleted** : 
  
- HandsOffFromNormal
    
- HandsOffAfterSave
    
- NoScribble
    
## <a name="notes-to-implementers"></a>针对实现者的说明

**SaveCompleted**方法可以执行几种可能的操作, 具体取决于邮件指针参数所包含的内容, 以及邮件的状态。 但是, 当操作成功时, 请始终保存_pMessage_参数指向的邮件的当前状态, 并将该表单转换为[正常](normal-state.md)状态。 
  
下表介绍了影响您在**SaveCompleted**实现过程中应执行的操作的条件。
  
|**条件**|**操作**|
|:-----|:-----|
|_pMessage_参数为 NULL, [IPersistMessage:: Save](ipersistmessage-save.md)方法的_fSameAsLoad_参数设置为 TRUE。  <br/> |调用所有已注册查看器的[IMAPIViewAdviseSink:: OnSaved](imapiviewadvisesink-onsaved.md)方法, 将该窗体标记为干净, 并返回 S_OK。  <br/> |
|_pMessage_参数为 NULL, **IPersistMessage:: Save**方法的_fSameAsLoad_参数设置为 FALSE。  <br/> |返回 S_OK。  <br/> |
|表单处于 "HandsOffFromNormal" 状态。  <br/> |释放当前邮件并将其替换为_pMessage_参数所指向的邮件。 调用替换邮件的[IUnknown:: AddRef](https://msdn.microsoft.com/library/b4316efd-73d4-4995-b898-8025a316ba63%28Office.15%29.aspx)方法并返回 S_OK。  <br/> |
|表单处于 "HandsOffAfterSave" 状态。  <br/> |调用所有已注册查看器的**IMAPIViewAdviseSink:: OnSaved**方法, 将该窗体标记为干净, 并返回 S_OK。  <br/> |
|表单处于 " [NoScribble](noscribble-state.md) " 状态。  <br/> |释放当前邮件并将其替换为_pMessage_指向的邮件。 调用替换邮件的**IUnknown:: AddRef**方法。 调用所有已注册查看器的**IMAPIViewAdviseSink:: OnSaved**方法, 将该窗体标记为干净, 并返回 S_OK。  <br/> |
|表单处于 HandsOff 状态之一, _pMessage_参数设置为 NULL。  <br/> |返回 E_INVALIDARG。  <br/> |
|表单处于 HandsOff 状态或 NoScribble 状态之外的状态。  <br/> |返回 E_UNEXPECTED。  <br/> |
   
有关保存存储对象的详细信息, 请参阅[IPersistStorage:: SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted)或[IPersistFile:: SaveCompleted](https://docs.microsoft.com/windows/desktop/api/objidl/nf-objidl-ipersistfile-savecompleted)方法的相关文档。 
  
## <a name="see-also"></a>另请参阅

- [IPersistMessage : IUnknown](ipersistmessageiunknown.md)
- [表单状态](form-states.md)
