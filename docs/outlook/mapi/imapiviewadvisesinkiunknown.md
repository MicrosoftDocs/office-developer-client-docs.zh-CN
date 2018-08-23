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
ms.openlocfilehash: 157703fc9702bb954b4a5c570fc3d5c045e181cc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567186"
---
# <a name="imapiviewadvisesink--iunknown"></a>IMAPIViewAdviseSink : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
从窗体接收通知。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
|由公开：  <br/> |查看建议接收器对象  <br/> |
|通过实现：  <br/> |表单查看器  <br/> |
|调用：  <br/> |窗体对象  <br/> |
|接口标识符：  <br/> |IID_IMAPIViewAdviseSink  <br/> |
|指针类型：  <br/> |LPMAPIVIEWADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[OnShutdown](imapiviewadvisesink-onshutdown.md) <br/> |通知表单查看器正在关闭窗体。  <br/> |
|[OnNewMessage](imapiviewadvisesink-onnewmessage.md) <br/> |通知表单查看器的新或现有邮件已加载的窗体。  <br/> |
|[OnPrint](imapiviewadvisesink-onprint.md) <br/> |通知窗体的打印状态的表单查看器。  <br/> |
|[OnSubmitted](imapiviewadvisesink-onsubmitted.md) <br/> |通知表单查看器的当前消息，已提交到 MAPI 后台处理程序。  <br/> |
|[OnSaved](imapiviewadvisesink-onsaved.md) <br/> |通知已保存窗体中的当前消息表单查看器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

