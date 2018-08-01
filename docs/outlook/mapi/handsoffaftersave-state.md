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
ms.openlocfilehash: 4bc4d680903d81b51a39ed39db3861597443d116
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775069"
---
# <a name="handsoffaftersave-state"></a>HandsOffAfterSave 状态

  
  
**适用于**： Outlook 
  
HandsOffAfterSave 状态是将窗体的内容保存到永久存储过程的一部分。 在此状态下，窗体对象应避免更改消息的属性的值的内存中副本因为可能没有其他机会保存这些更改。 下表介绍允许的 HandsOffAfterSave 状态转换。
  
|**IPersistMessage 方法**|**操作**|**新的状态**|
|:-----|:-----|:-----|
|[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)(_pMessage ！ =_ NULL)  <br/> |打开任何嵌入的对象。 保证_pMessage_中存储的邮件中的数据与以前的[IPersistMessage::Save](ipersistmessage-save.md)呼叫中的消息。 如果**SaveCompleted**调用成功，则输入正常状态。 否则为设置为 E_OUTOFMEMORY 的最后一个错误，并保持 HandsOffAfterSave 状态。  <br/> |[普通](normal-state.md)或 HandsOffAfterSave  <br/> |
|**IPersistMessage::SaveCompleted**(_pMessage = =_ NULL)  <br/> |设置为 E_INVALIDARG 或 E_UNEXPECTED 的最后一个错误。  <br/> |HandsOffAfterSave  <br/> |
|[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md)、**保存**或[IPersistMessage::InitNew](ipersistmessage-initnew.md) <br/> |设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
|[IPersistMessage::Load](ipersistmessage-load.md) <br/> |从目标邮件加载数据的窗体对象。 Form 对象转到文件夹中的下一页或上一页消息时，可能出现此呼叫。  <br/> |常规  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回的最后一个错误。  <br/> |HandsOffAfterSave  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法  <br/> |设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

