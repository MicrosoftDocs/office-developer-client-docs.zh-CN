---
title: IMAPIOfflineMgr IMAPIOffline
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr
api_type:
- COM
ms.assetid: 3e430308-190c-c9bb-fffc-c26ffecb73a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 235c2afb20e6f36df72eac4070c1df5fd10fcce8
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397049"
---
# <a name="imapiofflinemgr--imapioffline"></a>IMAPIOfflineMgr : IMAPIOffline

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有关连接的用户帐户的状态更改通知回调的注册的支持。
  
|||
|:-----|:-----|
|导出：  <br/> |msmapi32.dll  <br/> |
|实现者：  <br/> |Outlook  <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIOfflineMgr  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[建议](imapiofflinemgr-advise.md) <br/> |有关连接更改的通知回调的注册。  <br/> |
|[取消通知](imapiofflinemgr-unadvise.md) <br/> |删除通知回调给定的注册。  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是一个占位符，不支持。*  <br/> |
   
## <a name="remarks"></a>说明

在打开用户帐户配置文件使用**[HrOpenOfflineObj](hropenofflineobj.md)** 脱机对象时，客户端获取脱机支持**IMAPIOfflineMgr**的对象。 
  
由于从**[iunknown 导出](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)** 继承此接口，客户端可以此接口查询 （通过使用**[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)** ） 以获取支持**[IMAPIOffline](imapiofflineiunknown.md)** 的对象。 然后，客户端可以找出有关 （通过调用**[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)** )，脱机对象的回调功能，并选择设置回调 （通过使用**IMAPIOfflineMgr::Advise** ）。 
  
大部分此接口中的成员保留供内部使用的 Outlook 的占位符，并受到更改。 此接口的呼叫者必须使用非占位符成员仅为记录。
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline : IUnknown](imapiofflineiunknown.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)
  
[MAPI 接口](mapi-interfaces.md)

