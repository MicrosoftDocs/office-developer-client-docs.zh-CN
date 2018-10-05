---
title: IMAPIOffline IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline
api_type:
- COM
ms.assetid: 211281ff-3c22-1b51-4b72-ca1e313c7202
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20d8c39765b0dbbfdde530361894d0a27876010a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401277"
---
# <a name="imapioffline--iunknown"></a>IMAPIOffline : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供脱机对象的信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)查询 <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIOffline  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|**[SetCurrentState](imapioffline-setcurrentstate.md)** <br/> |设置为联机或脱机脱机对象的当前状态。  <br/> |
|**[GetCapabilities](imapioffline-getcapabilities.md)** <br/> |获取为其脱机对象支持回调的条件。  <br/> |
|**[GetCurrentState](imapioffline-getcurrentstate.md)** <br/> |获取一个脱机对象的当前联机或脱机状态。  <br/> |
| *占位符成员*  <br/> |此成员是一个占位符，不支持。  <br/> |
   
## <a name="remarks"></a>说明

客户端使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开并获取支持**IMAPIOfflineMgr**脱机对象。 由于**IMAPIOfflineMgr**继承从[iunknown 导出](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)，客户端可以此接口查询 （通过使用[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)） 来获取**IMAPIOffline**脱机对象指向的接口指针的指针。 客户端然后可以获取或设置对象的当前状态或找出有关对象的回调功能 （通过调用**IMAPIOffline::GetCapabilities** ） 并选择使用**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)** 设置回调。 
  
此接口中的成员保留供内部使用的 Microsoft Outlook 2013 的占位符并可能会更改。 必须只记录使用此接口中的其他成员。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[MAPI 接口](mapi-interfaces.md)

