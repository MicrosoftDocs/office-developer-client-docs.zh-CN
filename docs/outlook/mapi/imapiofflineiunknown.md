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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321264"
---
# <a name="imapioffline--iunknown"></a>IMAPIOffline : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供脱机对象的信息。
  
|||
|:-----|:-----|
|提供者：  <br/> |[IMAPIOfflineMgr 查询](imapiofflinemgrimapioffline.md) <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIOffline  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|**[SetCurrentState](imapioffline-setcurrentstate.md)** <br/> |将脱机对象的当前状态设置为联机或脱机。  <br/> |
|**[GetCapabilities](imapioffline-getcapabilities.md)** <br/> |获取脱机对象支持回调的条件。  <br/> |
|**[GetCurrentState](imapioffline-getcurrentstate.md)** <br/> |获取脱机对象的当前联机或脱机状态。  <br/> |
| *占位符成员*  <br/> |此成员是占位符，不受支持。  <br/> |
   
## <a name="remarks"></a>备注

客户端使用 **[HrOpenOfflineObj](hropenofflineobj.md)** 打开并获取支持 **IMAPIOfflineMgr** 的脱机对象。 由于 **IMAPIOfflineMgr** 继承自 [IUnknown，](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)因此客户端可以使用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)) 查询此接口 (以获取指向脱机对象的 **IMAPIOffline** 接口指针的指针。 然后，客户端可以获取或设置对象的当前状态，或者通过调用 **IMAPIOffline：：GetCapabilities** ) 了解对象 (的回调功能，并选择使用 **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)** 设置回调。 
  
此接口中的成员是保留供内部使用的占位符Microsoft Outlook 2013可能会更改。 此接口中的其他成员必须仅用于记录。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[MAPI 接口](mapi-interfaces.md)

