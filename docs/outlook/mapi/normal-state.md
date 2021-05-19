---
title: 正常状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8b2acad7-5ef8-44db-911f-3bd2a7ca2778
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d7b50a92c58dd7ab1f03cb4cf84acc2d4a2b404b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335740"
---
# <a name="normal-state"></a>正常状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
"正常"状态是表单对象花费大部分时间等待客户端应用程序启动操作（如保存更改或关闭表单）的地方。 下表介绍了允许从 Normal 状态转换。
  
|**IPersistMessage 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage：：Save](ipersistmessage-save.md) (_pMessage ==_ NULL，fSameAsLoad  _==_ TRUE)   <br/> - 或 -  <br/> **IPersistMessage：：Save** _(pMessage ！=_ NULL，fSameAsLoad  _==_ FALSE)   <br/> |递归保存任何已修改的嵌入 OLE 对象。 将邮件数据保存回 message 对象。 存储  _fSameAsLoad_ 标志，供以后在 [NoScribble 状态使用](noscribble-state.md) 。  <br/> |NoScribble  <br/> |
|**IPersistMessage：：Save** (_pMessage ！=_  _NULL，fSameAsLoad ==_ TRUE)   <br/> |这一点与上一种情况相同，只不过此 **Save** 调用在内存不足的情况下使用，并且不得因内存不足而失败。  <br/> |NoScribble  <br/> |
|[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) <br/> |对嵌入的邮件递归调用 **HandsOffMessage** 方法，或对嵌入的 OLE 对象调用 OLE [IPersistStorage：：HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx) 方法。 释放邮件对象和任何嵌入的邮件或对象。  <br/> |[HandsOffFromNormal](handsofffromnormal-state.md) <br/> |
|[IPersistMessage：：SaveCompleted](ipersistmessage-savecompleted.md) [、IPersistMessage：：InitNew](ipersistmessage-initnew.md) 或 [IPersistMessage：：Load](ipersistmessage-load.md) <br/> |将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |一般  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回最后一个错误。  <br/> |一般  <br/> |
|其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法  <br/> |实现如 [IPersistMessage ： IUnknown 接口的文档](ipersistmessageiunknown.md) 中所述。  <br/> |一般  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

