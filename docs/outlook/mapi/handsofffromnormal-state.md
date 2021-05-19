---
title: HandsOffFromNormal 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1afe6a2e-a5e6-4844-9f82-908894fc6759
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 17fa0f3d4e74ce7d717a94378880f2cc46150fc2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426469"
---
# <a name="handsofffromnormal-state"></a>HandsOffFromNormal 状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
HandsOffFromNormal 状态非常类似于 [HandsOffAfterSave](handsoffaftersave-state.md) 状态。 它是将表单的内容保存为永久存储的过程的一部分。 在此状态中时，form 对象应避免对邮件属性值的内存中副本进行更改，因为可能再没有保存这些更改的机会。 下表介绍了允许从 HandsOffFromNormal 状态转换。 
  
|IPersistMessage** 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) _(pMessage ！=_ NULL)   <br/> |将邮件对象的邮件替换为  _pMessage_，这是上一次调用 [IPersistMessage：：HandsOffMessage 时吊销的邮件的替换](ipersistmessage-handsoffmessage.md)。 新邮件中的数据保证与吊销的邮件中的数据相同。 不应将邮件标记为干净，也不应在此调用后调用[IMAPIViewAdviseSink：：OnSaved。](imapiviewadvisesink-onsaved.md) 如果 **SaveCompleted** 调用成功，请输入 [Normal](normal-state.md) 状态。 否则，请保持 HandsOffFromNormal 状态。  <br/> |Normal 或 HandsOffFromNormal  <br/> |
|**IPersistMessage：：SaveCompleted** (_pMessage ==_ NULL)   <br/> |将最后一个错误设置为E_UNEXPECTED。  <br/> |HandsOffFromNormal  <br/> |
|**HandsOffMessage** [、IPersistMessage：：Save、IPersistMessage：：InitNew](ipersistmessage-save.md)或 [IPersistMessage：：Load](ipersistmessage-load.md) [](ipersistmessage-initnew.md) <br/> |将最后一个错误设置为E_UNEXPECTED。  <br/> |HandsOffFromNormal  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回最后一个错误。  <br/> |HandsOffFromNormal  <br/> |
|其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法  <br/> |将最后一个错误设置为E_UNEXPECTED。  <br/> |HandsOffFromNormal  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

