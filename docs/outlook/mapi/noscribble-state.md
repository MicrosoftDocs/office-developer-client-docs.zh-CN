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
  
NoScribble 状态指示正在保存对邮件所做的更改。 当 form 对象的[IPersistMessage:: Save](ipersistmessage-save.md)方法由客户端应用程序调用时, 将会实际保存在表单对象的用户界面中存储的值。 下表介绍了允许从 NoScribble 状态进行的转换。 
  
|IPersistMessage * * 方法 * *|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage = =_ NULL)  <br/> |如果[IPersistMessage:: Save](ipersistmessage-save.md)调用导致窗体进入 NoScribble 状态且邮件已修改, 则在内部将更改标记为 "已保存" 并调用[IMAPIViewAdviseSink:: OnSaved](imapiviewadvisesink-onsaved.md) , 则为_fSameAsLoad_标志为 TRUE::种.  <br/> |[Normal](normal-state.md) <br/> |
|**IPersistMessage:: SaveCompleted**(_pMessage! =_ NULL)  <br/> |调用[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)方法 (类似于 OLE [IPersistStorage:: HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法), 后接正常的**SaveCompleted**操作。 如果**SaveCompleted**成功, 则输入正常状态。 否则, 请输入[HandsOffAfterSave](handsoffaftersave-state.md)状态。  <br/> |Normal 或 HandsOffAfterSave  <br/> |
|**HandsOffMessage** <br/> |对嵌入的邮件或 ole **IPersistStorage:: HandsOffStorage**方法, 对嵌入的 ole 对象以递归方式调用**HandsOffMessage**方法。 释放邮件对象和任何嵌入的邮件或对象。  <br/> |HandsOffAfterSave  <br/> |
|**Save**、 [IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md) <br/> |将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |NoScribble  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回上一个错误。  <br/> |NoScribble  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法  <br/> |将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |NoScribble  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

