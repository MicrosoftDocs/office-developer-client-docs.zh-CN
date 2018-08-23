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
ms.openlocfilehash: adcb8e78d4e85e19d4102795aa4d43f06a7f86ba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568145"
---
# <a name="imapiofflinenotify--iunknown"></a>IMAPIOfflineNotify : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
支持 Microsoft Outlook 2010 和 Microsoft Outlook 2013 中向客户端发送通知回调。
  
|||
|:-----|:-----|
|提供者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIOfflineNotify  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[Notify](imapiofflinenotify-notify.md) <br/> |将通知发送到客户端有关连接状态的变化。  <br/> |
   
## <a name="remarks"></a>注解

客户端必须实现此接口，并将指针传递给它为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员设置使用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 回调时。 随后，Outlook 2010 或 Outlook 2013 都将能够使用此接口到客户端发送通知回调。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)

