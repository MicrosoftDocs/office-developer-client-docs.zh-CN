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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406603"
---
# <a name="handsoffaftersave-state"></a>HandsOffAfterSave 状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
HandsOffAfterSave 状态是将表单的内容保存为永久存储过程的一部分。 在此状态中时，form 对象应避免对邮件属性值的内存中副本进行更改，因为可能再没有保存这些更改的机会。 下表介绍了允许从 HandsOffAfterSave 状态转换。
  
|**IPersistMessage 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) _(pMessage ！=_ NULL)   <br/> |打开任何嵌入的对象。 _pMessage_ 中存储的邮件数据保证与上一 [个 IPersistMessage：：Save](ipersistmessage-save.md)调用中的邮件相同。 如果 **SaveCompleted** 调用成功，请输入 Normal 状态。 否则，将最后一个错误设置为 E_OUTOFMEMORY并保持 HandsOffAfterSave 状态。  <br/> |[Normal](normal-state.md) 或 HandsOffAfterSave  <br/> |
|**IPersistMessage：：SaveCompleted** (_pMessage ==_ NULL)   <br/> |将最后一个错误设置为E_INVALIDARG或E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
|[IPersistMessage：：HandsOffMessage、Save](ipersistmessage-handsoffmessage.md)或[IPersistMessage：：InitNew](ipersistmessage-initnew.md)  <br/> |将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
|[IPersistMessage::Load](ipersistmessage-load.md) <br/> |使用来自目标邮件的数据加载表单对象。 当窗体对象发送到文件夹中的下一封邮件或上一封邮件时，可能会发生此调用。  <br/> |一般  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回最后一个错误。  <br/> |HandsOffAfterSave  <br/> |
|其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法  <br/> |将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |HandsOffAfterSave  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

