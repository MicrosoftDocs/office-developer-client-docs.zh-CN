---
title: 未初始化状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e071b50f-2e75-4537-ac7b-4a2f5ebea83d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: be35c9d3f8fc7badf83086e63e4c94e0efa4d5bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425559"
---
# <a name="uninitialized-state"></a>未初始化状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
"未初始化"状态是首次创建对象时它们应位于的初始状态表单对象。 当客户端应用程序对表单对象调用 [IPersistMessage：：InitNew](ipersistmessage-initnew.md) 或 [IPersistMessage：：Load](ipersistmessage-load.md) 方法时，Form 对象会使用邮件数据进行初始化。 下表介绍了允许从单一化状态转换。 
  
|**IPersistMessage 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage::InitNew](ipersistmessage-initnew.md) <br/> |使用默认数据加载表单对象。  <br/> |[Normal](normal-state.md) <br/> |
|[IPersistMessage::Load](ipersistmessage-load.md) <br/> |使用来自目标邮件的数据加载表单对象。  <br/> |一般  <br/> |
|[IPersistMessage::GetClassID](ipersistmessage-getclassid.md) <br/> |返回成功，或将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |未初始化  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回最后一个错误。  <br/> |未初始化  <br/> |
|其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法  <br/> |将最后一个错误设置为 并返回E_UNEXPECTED。  <br/> |未初始化  <br/> |
   
## <a name="see-also"></a>另请参阅



[正常状态](normal-state.md)
  
[表单状态](form-states.md)

