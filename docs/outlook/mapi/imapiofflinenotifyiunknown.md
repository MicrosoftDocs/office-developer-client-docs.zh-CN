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
ms.openlocfilehash: 37f21c438a0a337eecf5c15a27a0b891d19bcfb8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775501"
---
# <a name="imapiofflinenotify--iunknown"></a>IMAPIOfflineNotify : IUnknown

  
  
**适用于**： Outlook 
  
支持 Microsoft Outlook 2010 和 Microsoft Outlook 2013 中向客户端发送通知回调。
  
|||
|:-----|:-----|
|提供者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIOfflineNotify  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[Notify](imapiofflinenotify-notify.md) <br/> |将通知发送到客户端有关连接状态的变化。  <br/> |
   
## <a name="remarks"></a>说明

客户端必须实现此接口，并将指针传递给它为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员设置使用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 回调时。 随后，Outlook 2010 或 Outlook 2013 都将能够使用此接口到客户端发送通知回调。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)

