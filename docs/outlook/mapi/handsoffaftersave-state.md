---
title: HandsOffAfterSave 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffdfed49-2c52-445c-8051-6e566f61eedc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85630965c7e78e6fa76e348bfe98cc9060665057
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299522"
---
# <a name="handsoffaftersave-state"></a>HandsOffAfterSave 状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
HandsOffAfterSave 状态是将表单内容保存到永久存储的过程的一部分。 在此状态下, form 对象应避免对邮件属性值的内存中的值进行更改, 因为可能没有其他机会保存这些更改。 下表介绍了允许从 HandsOffAfterSave 状态进行的转换。
  
|**IPersistMessage 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage! =_ NULL)  <br/> |打开任何嵌入的对象。 _pMessage_中存储的邮件中的数据保证与前[IPersistMessage:: Save](ipersistmessage-save.md)调用中的邮件相同。 如果**SaveCompleted**调用成功, 则输入正常状态。 否则, 将最后一个错误设置为 E_OUTOFMEMORY, 并保持 HandsOffAfterSave 状态。  <br/> |[Normal](normal-state.md)或 HandsOffAfterSave  <br/> |
|**IPersistMessage:: SaveCompleted**(_pMessage = =_ NULL)  <br/> |将最后一个错误设置为 E_INVALIDARG 或 E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
|[IPersistMessage:: HandsOffMessage](ipersistmessage-handsoffmessage.md)、 **Save**或[IPersistMessage:: InitNew](ipersistmessage-initnew.md) <br/> |将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
|[IPersistMessage::Load](ipersistmessage-load.md) <br/> |使用目标邮件中的数据加载 form 对象。 当窗体对象转到文件夹中的下一封邮件或上一封邮件时, 可能会发生此调用。  <br/> |一般  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回上一个错误。  <br/> |HandsOffAfterSave  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法  <br/> |将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

