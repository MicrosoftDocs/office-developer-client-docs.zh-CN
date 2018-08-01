---
title: Normal 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b2acad7-5ef8-44db-911f-3bd2a7ca2778
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dcc92d220f07b1c111284acacac4a65a2e3f8b6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776528"
---
# <a name="normal-state"></a>Normal 状态

  
  
**适用于**： Outlook 
  
正常状态是时间的其中 form 对象花费大量其启动操作，如保存更改，或关闭窗体的客户端应用程序等待。 下表介绍允许的切换从正常状态。
  
|**IPersistMessage 方法**|**操作**|**新的状态**|
|:-----|:-----|:-----|
|[IPersistMessage::Save](ipersistmessage-save.md)(_pMessage = =_ NULL， _fSameAsLoad = =_ ，则返回 TRUE)  <br/> -或者-  <br/> **IPersistMessage::Save**(_pMessage ！ =_ NULL， _fSameAsLoad = =_ FALSE)  <br/> |以递归方式保存已修改的任何嵌入的 OLE 对象。 将邮件数据保存回 message 对象。 存储在[NoScribble](noscribble-state.md)状态以供以后使用_fSameAsLoad_标志。  <br/> |NoScribble  <br/> |
|**IPersistMessage::Save**(_pMessage ！ =_ NULL， _fSameAsLoad = =_ ，则返回 TRUE)  <br/> |这是相同的以前的情况下，只不过此**保存**呼叫中内存不足的情况下使用和不得缺少内存导致失败。  <br/> |NoScribble  <br/> |
|[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) <br/> |以递归方式调用嵌入邮件上的**HandsOffMessage**方法或嵌入的 OLE 对象的 OLE [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法。 发布的消息对象和任何嵌入式的邮件或对象。  <br/> |[HandsOffFromNormal](handsofffromnormal-state.md) <br/> |
|[IPersistMessage::SaveCompleted](ipersistmessage-savecompleted.md)、 [IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md) <br/> |设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |常规  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回的最后一个错误。  <br/> |常规  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法  <br/> |实现的文档中所述[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口。  <br/> |常规  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

