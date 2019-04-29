---
title: IMAPISyncProgressCallback IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISyncProgressCallback
api_type:
- COM
ms.assetid: 146b5e36-8d73-4949-9fed-1074f707423d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 54f61eb1bf111601e8b2c889b0d2890d0c10d63b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418335"
---
# <a name="imapisyncprogresscallback--iunknown"></a>IMAPISyncProgressCallback : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在调用[IMAPISync: SynchronizeInBackground](imapisyncsynchronizeinbackground.md)过程中, 会将存储提供程序作为字段传递给 MAPISIB 结构。 存储提供程序使用此接口向 Microsoft Outlook 提供有关同步状态的反馈。
  
|||
|:-----|:-----|
|标头文件：  <br/> ||
|公开者:  <br/> |Outlook  <br/> |
|实现者：  <br/> |Outlook  <br/> |
|调用者：  <br/> |存储提供程序  <br/> |
|接口标识符:  <br/> |IID_IMAPISyncProgressCallback  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Progress](imapisyncprogresscallback-progress.md) <br/> |存储提供程序定期调用此函数以更新 "发送/接收" 对话框中的状态。  <br/> |
|[错误](imapisyncprogresscallback-error.md) <br/> |如果在同步过程中遇到错误, 则存储提供程序将调用此函数, 以提供在 "发送/接收" 对话框中显示的详细信息。  <br/> |
|[完成](imapisyncprogresscallback-done.md) <br/> |存储提供程序调用此函数来通知 Outlook 同步已完成。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISync : IUnknown](imapisynciunknown.md)


[MAPI 接口](mapi-interfaces.md)

