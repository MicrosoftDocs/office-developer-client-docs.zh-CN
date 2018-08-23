---
title: NoScribble 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0246138f-c55e-4353-8e53-e973f524d52c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 119d162b50048e69168aa864e5d19ad806758456
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575992"
---
# <a name="noscribble-state"></a>NoScribble 状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
NoScribble 状态指示邮件的更改将被保存。 Form 对象的[IPersistMessage::Save](ipersistmessage-save.md)方法由客户端应用程序时发生实际将保存 form 对象的用户界面中存储的值。 下表介绍允许的 NoScribble 状态转换。 
  
|IPersistMessage * * 方法 * *|**操作**|**新的状态**|
|:-----|:-----|:-----|
|[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage = =_ NULL)  <br/> |如果_fSameAsLoad_标志上已 TRUE [IPersistMessage::Save](ipersistmessage-save.md)呼叫导致该窗体输入 NoScribble 状态和邮件已被修改、 内部标记为已保存的更改，并调用[IMAPIViewAdviseSink::OnSaved](imapiviewadvisesink-onsaved.md)方法。  <br/> |[Normal](normal-state.md) <br/> |
|**IPersistMessage::SaveCompleted**(_pMessage ！ =_ NULL)  <br/> |调用[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)方法 （类似于 OLE [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法） 跟普通**SaveCompleted**操作。 如果**SaveCompleted**成功，则输入正常状态。 否则，请输入[HandsOffAfterSave](handsoffaftersave-state.md)状态。  <br/> |普通或 HandsOffAfterSave  <br/> |
|**HandsOffMessage** <br/> |以递归方式调用嵌入邮件上的**HandsOffMessage**方法或嵌入的 OLE 对象的 OLE **IPersistStorage::HandsOffStorage**方法。 发布的消息对象和任何嵌入式的邮件或对象。  <br/> |HandsOffAfterSave  <br/> |
|**保存**、 [IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md) <br/> |设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |NoScribble  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回的最后一个错误。  <br/> |NoScribble  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法  <br/> |设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |NoScribble  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

