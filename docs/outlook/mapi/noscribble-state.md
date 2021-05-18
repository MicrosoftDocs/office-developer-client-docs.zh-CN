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
ms.openlocfilehash: 239f11cf27cdebff3d51645319d7ada3b9bb9ff6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326199"
---
# <a name="noscribble-state"></a>NoScribble 状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
NoScribble 状态指示正在保存对邮件的更改。 当客户端应用程序调用表单对象的 [IPersistMessage：：Save](ipersistmessage-save.md) 方法时，将实际保存表单对象用户界面中存储的值。 下表介绍了允许从 NoScribble 状态转换。 
  
|IPersistMessage** 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) (_pMessage ==_ NULL)   <br/> |如果  _fSameAsLoad_ 标记在导致表单进入 NoScribble 状态且消息已修改的 [IPersistMessage：：Save](ipersistmessage-save.md) 调用上为 TRUE，请在内部将更改标记为已保存并调用 [IMAPIViewAdviseSink：：OnSaved](imapiviewadvisesink-onsaved.md) 方法。  <br/> |[Normal](normal-state.md) <br/> |
|**IPersistMessage：：SaveCompleted** _(pMessage ！=_ NULL)   <br/> |调用 [IPersistMessage：：HandsOffMessage](ipersistmessage-handsoffmessage.md) 方法 (类似于 OLE [IPersistStorage：：HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) 方法) 后跟常规 **SaveCompleted** 操作。 如果 **SaveCompleted** 成功，请输入 Normal 状态。 否则，输入 [HandsOffAfterSave](handsoffaftersave-state.md) 状态。  <br/> |Normal 或 HandsOffAfterSave  <br/> |
|**HandsOffMessage** <br/> |对嵌入的邮件递归调用 **HandsOffMessage** 方法，或对嵌入的 OLE 对象调用 OLE **IPersistStorage：：HandsOffStorage** 方法。 释放邮件对象和任何嵌入的邮件或对象。  <br/> |HandsOffAfterSave  <br/> |
|**Save** [、IPersistMessage：：InitNew](ipersistmessage-initnew.md)或 [IPersistMessage：：Load](ipersistmessage-load.md) <br/> |将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |NoScribble  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回最后一个错误。  <br/> |NoScribble  <br/> |
|其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法  <br/> |将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |NoScribble  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

