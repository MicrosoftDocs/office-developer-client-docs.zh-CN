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
ms.openlocfilehash: d0b7baf4ab17d12145170961a43ca4be252146a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775077"
---
# <a name="handsofffromnormal-state"></a>HandsOffFromNormal 状态

  
  
**适用于**： Outlook 
  
非常类似于[HandsOffAfterSave](handsoffaftersave-state.md)状态 HandsOffFromNormal 状态。 它是将窗体的内容保存到永久存储过程的一部分。 在此状态下，窗体对象应避免更改消息的属性的值的内存中副本因为可能没有其他机会保存这些更改。 下表介绍允许的 HandsOffFromNormal 状态转换。 
  
|IPersistMessage * * 方法 * *|**操作**|**新的状态**|
|:-----|:-----|:-----|
|[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage ！ =_ NULL)  <br/> |将 message 对象的消息替换_pMessage_，这是替换为[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)到以前的呼叫被吊销的邮件。 在新邮件中的数据保证是已吊销消息相同。 不应将邮件标记为干净，也不应[IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md)调用后此呼叫。 如果**SaveCompleted**调用成功，则输入[正常](normal-state.md)状态。 否则，保持 HandsOffFromNormal 状态。  <br/> |普通或 HandsOffFromNormal  <br/> |
|**IPersistMessage::SaveCompleted**(_pMessage = =_ NULL)  <br/> |设置为 E_UNEXPECTED 最后一个错误。  <br/> |HandsOffFromNormal  <br/> |
|**HandsOffMessage**、 [IPersistMessage::Save](ipersistmessage-save.md)、 [IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md) <br/> |设置为 E_UNEXPECTED 最后一个错误。  <br/> |HandsOffFromNormal  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回的最后一个错误。  <br/> |HandsOffFromNormal  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法  <br/> |设置为 E_UNEXPECTED 最后一个错误。  <br/> |HandsOffFromNormal  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

