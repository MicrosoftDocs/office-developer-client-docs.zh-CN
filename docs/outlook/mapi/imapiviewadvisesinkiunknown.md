---
title: IMAPIViewAdviseSink IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink
api_type:
- COM
ms.assetid: 1231391d-803a-4b41-b252-4d986f99361a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 70f61fe33baa7870a58c4cbc7d75e0df119b5b1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351137"
---
# <a name="imapiviewadvisesink--iunknown"></a>IMAPIViewAdviseSink : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接收来自表单的通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|公开者:  <br/> |查看建议接收器对象  <br/> |
|实现者：  <br/> |表单查看器  <br/> |
|调用者：  <br/> |表单对象  <br/> |
|接口标识符:  <br/> |IID_IMAPIViewAdviseSink  <br/> |
|指针类型:  <br/> |LPMAPIVIEWADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[OnShutdown](imapiviewadvisesink-onshutdown.md) <br/> |通知表单查看器表单正在关闭。  <br/> |
|[OnNewMessage](imapiviewadvisesink-onnewmessage.md) <br/> |通知表单查看器新的或现有的邮件已加载到表单中。  <br/> |
|[OnPrint](imapiviewadvisesink-onprint.md) <br/> |将表单的打印状态通知给表单查看器。  <br/> |
|[OnSubmitted](imapiviewadvisesink-onsubmitted.md) <br/> |通知表单查看器当前邮件已提交到 MAPI 后台处理程序。  <br/> |
|[OnSaved](imapiviewadvisesink-onsaved.md) <br/> |通知表单查看器表单中的当前邮件已保存。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

