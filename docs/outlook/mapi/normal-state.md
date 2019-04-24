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
  
正常状态是 form 对象的大部分时间, 等待客户端应用程序启动操作 (如保存更改或关闭窗体)。 下表介绍了允许从正常状态进行的转换。
  
|**IPersistMessage 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage:: Save](ipersistmessage-save.md)(_pMessage = =_ NULL, _fSameAsLoad = =_ TRUE)  <br/> - 或 -  <br/> **IPersistMessage:: Save**(_pMessage! =_ NULL, _fSameAsLoad = =_ FALSE)  <br/> |以递归方式保存所有已修改的嵌入 OLE 对象。 将邮件数据保存回 message 对象。 存储_fSameAsLoad_标志以供以后在[NoScribble](noscribble-state.md)状态中使用。  <br/> |NoScribble  <br/> |
|**IPersistMessage:: Save**(_pMessage! =_ NULL, _fSameAsLoad = =_ TRUE)  <br/> |这与前一种情况相同, 不同之处在于此**保存**调用在内存不足的情况下使用, 如果内存不足, 则不能失败。  <br/> |NoScribble  <br/> |
|[IPersistMessage::HandsOffMessage](ipersistmessage-handsoffmessage.md) <br/> |对嵌入的邮件或 ole [IPersistStorage:: HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d%28Office.15%29.aspx)方法, 对嵌入的 ole 对象以递归方式调用**HandsOffMessage**方法。 释放邮件对象和任何嵌入的邮件或对象。  <br/> |[HandsOffFromNormal](handsofffromnormal-state.md) <br/> |
|[IPersistMessage:: SaveCompleted](ipersistmessage-savecompleted.md), [IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md) <br/> |将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |一般  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回上一个错误。  <br/> |一般  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法  <br/> |按照[IPersistMessage: IUnknown](ipersistmessageiunknown.md)接口的文档中所述实现。  <br/> |一般  <br/> |
   
## <a name="see-also"></a>另请参阅



[表单状态](form-states.md)

