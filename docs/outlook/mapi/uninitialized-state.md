---
title: Uninitialized 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e071b50f-2e75-4537-ac7b-4a2f5ebea83d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 95ed80a6d0ea6a6a7c8cc768b32981ac899b69e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578246"
---
# <a name="uninitialized-state"></a>Uninitialized 状态

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
未初始化的状态是首次创建时，对象应中的初始状态窗体。 客户端应用程序在窗体对象上调用[IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)方法时，使用消息数据成为初始化表单对象。 下表介绍允许的 Unitialized 状态转换。 
  
|**IPersistMessage 方法**|**操作**|**新的状态**|
|:-----|:-----|:-----|
|[IPersistMessage::InitNew](ipersistmessage-initnew.md) <br/> |加载表单对象的默认数据。  <br/> |[Normal](normal-state.md) <br/> |
|[IPersistMessage::Load](ipersistmessage-load.md) <br/> |从目标邮件加载数据的窗体对象。  <br/> |常规  <br/> |
|[IPersistMessage::GetClassID](ipersistmessage-getclassid.md) <br/> |返回成功，或设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |未初始化  <br/> |
|[IPersistMessage::GetLastError](ipersistmessage-getlasterror.md) <br/> |返回的最后一个错误。  <br/> |未初始化  <br/> |
|其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法  <br/> |设置为上一个错误，并返回 E_UNEXPECTED。  <br/> |未初始化  <br/> |
   
## <a name="see-also"></a>另请参阅



[Normal 状态](normal-state.md)
  
[表单状态](form-states.md)

