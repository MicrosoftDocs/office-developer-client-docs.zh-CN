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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429416"
---
# <a name="imapiviewadvisesink--iunknown"></a>IMAPIViewAdviseSink : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
接收来自表单的通知。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
|公开者：  <br/> |查看通知接收对象  <br/> |
|实现者：  <br/> |表单查看器  <br/> |
|调用者：  <br/> |表单对象  <br/> |
|接口标识符：  <br/> |IID_IMAPIViewAdviseSink  <br/> |
|指针类型：  <br/> |LPMAPIVIEWADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[OnShutdown](imapiviewadvisesink-onshutdown.md) <br/> |通知表单查看器正在关闭表单。  <br/> |
|[OnNewMessage](imapiviewadvisesink-onnewmessage.md) <br/> |通知表单查看器已在表单中加载了新邮件或现有邮件。  <br/> |
|[OnPrint](imapiviewadvisesink-onprint.md) <br/> |通知窗体查看者窗体的打印状态。  <br/> |
|[OnSubmitted](imapiviewadvisesink-onsubmitted.md) <br/> |通知表单查看器当前邮件已提交到 MAPI 后台处理程序。  <br/> |
|[OnSaved](imapiviewadvisesink-onsaved.md) <br/> |通知窗体查看器窗体中的当前邮件已保存。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

