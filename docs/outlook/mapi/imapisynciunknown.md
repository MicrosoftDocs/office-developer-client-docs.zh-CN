---
title: IMAPISync IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISync
api_type:
- COM
ms.assetid: c14d1012-f3d4-47eb-8a90-3160331f94e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4d46152136f3806c79f0dd454ed9fd41fc845721
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405589"
---
# <a name="imapisync--iunknown"></a>IMAPISync : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供用于同步电子邮件而不是使用传输 API 的机制。 此接口在 store 对象上公开。 通过使用此接口和[IMAPISyncProgressCallback: IUnknown](imapisyncprogresscallbackiunknown.md), 传输提供程序可以提供比 Microsoft Outlook 中的 "发送/接收" 对话框中显示的内容更好的进度和错误消息。
  
发件箱仍在默认存储中。 Outlook 将继续使用传输 api 发送邮件, 因为传出邮件不能位于外部存储中。
  
|||
|:-----|:-----|
|公开者:  <br/> |存储和传输提供程序  <br/> |
|实现者：  <br/> |Outlook  <br/> |
|调用者：  <br/> |存储和传输提供程序  <br/> |
|接口标识符:  <br/> |IID_IMAPISync  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[SynchronizeInBackground](imapisyncsynchronizeinbackground.md) <br/> |由邮件存储提供程序实现。 此方法由 outlook 2010 和 outlook 2013 调用以启动同步。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISyncProgressCallback : IUnknown](imapisyncprogresscallbackiunknown.md)


[MAPI 接口](mapi-interfaces.md)

