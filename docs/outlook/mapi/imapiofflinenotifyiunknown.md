---
title: IMAPIOfflineNotify IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineNotify
api_type:
- COM
ms.assetid: a593d2a1-29f8-7e23-85bf-02fa3cfebe1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 940cf0cf377f1b38071df5e3c300ccb7d685e5a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439875"
---
# <a name="imapiofflinenotify--iunknown"></a>IMAPIOfflineNotify : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持在向客户端发送通知回调时使用 microsoft outlook 2010 和 microsoft outlook 2013。
  
|||
|:-----|:-----|
|提供者：  <br/> |Client  <br/> |
|接口标识符:  <br/> |IID_IMAPIOfflineNotify  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Notify](imapiofflinenotify-notify.md) <br/> |向客户端发送有关连接状态更改的通知。  <br/> |
   
## <a name="remarks"></a>说明

在设置使用**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 的回调时, 客户端必须实现此接口并将指针作为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员进行传递。 随后, outlook 2010 或 outlook 2013 将能够使用此接口向客户端发送通知回调。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)

