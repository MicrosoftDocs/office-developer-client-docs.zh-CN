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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299466"
---
# <a name="handsofffromnormal-state"></a>HandsOffFromNormal 状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
HandsOffFromNormal 状态非常类似于[HandsOffAfterSave](handsoffaftersave-state.md)状态。 它是将表单内容保存到永久存储的过程的一部分。 在此状态下, form 对象应避免对邮件属性值的内存中的值进行更改, 因为可能没有其他机会保存这些更改。 下表介绍了允许从 HandsOffFromNormal 状态进行的转换。 
  
|IPersistMessage * * 方法 * *|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage! =_ NULL)  <br/> |将邮件对象的邮件替换为_pMessage_, 这是以前调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)吊销的邮件的替代邮件。 确保新邮件中的数据与吊销的邮件中的数据相同。 不应将邮件标记为 "干净", 也不应[IMAPIViewAdviseSink:: OnSaved](imapiviewadvisesink-onsaved.md)在此调用之后调用。 如果**SaveCompleted**调用成功, 则输入[正常](normal-state.md)状态。 否则, 保持 HandsOffFromNormal 状态。  <br/> |Normal 或 HandsOffFromNormal  <br/> |
|**IPersistMessage:: SaveCompleted**(_pMessage = =_ NULL)  <br/> |将最后一个错误设置为 E_UNEXPECTED。  <br/> |HandsOffFromNormal  <br/> |
|**HandsOffMessage**、 [IPersistMessage:: Save](ipersistmessage-save.md)、 [IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md) <br/> |将最后一个错误设置为 E_UNEXPECTED。  <br/> |HandsOffFromNormal  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回上一个错误。  <br/> |HandsOffFromNormal  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法  <br/> |将最后一个错误设置为 E_UNEXPECTED。  <br/> |HandsOffFromNormal  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

