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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360499"
---
# <a name="uninitialized-state"></a>未初始化状态

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
未初始化状态是首次创建窗体对象时, 它们应位于的初始状态。 当客户端应用程序对 form 对象调用[IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md)方法时, 窗体对象将被初始化为邮件数据。 下表介绍了允许从 Unitialized 状态进行的转换。 
  
|**IPersistMessage 方法**|**Action**|**新状态**|
|:-----|:-----|:-----|
|[IPersistMessage::InitNew](ipersistmessage-initnew.md) <br/> |使用默认数据加载 form 对象。  <br/> |[Normal](normal-state.md) <br/> |
|[IPersistMessage::Load](ipersistmessage-load.md) <br/> |使用目标邮件中的数据加载 form 对象。  <br/> |一般  <br/> |
|[IPersistMessage::GetClassID](ipersistmessage-getclassid.md) <br/> |返回 success, 或将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |即  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回上一个错误。  <br/> |即  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法  <br/> |将上一个错误设置为并返回 E_UNEXPECTED。  <br/> |即  <br/> |
   
## <a name="see-also"></a>另请参阅



[正常状态](normal-state.md)
  
[表单状态](form-states.md)

