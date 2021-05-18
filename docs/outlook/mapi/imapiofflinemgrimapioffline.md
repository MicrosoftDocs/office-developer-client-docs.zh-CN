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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270089"
---
# <a name="imapiofflinemgr--imapioffline"></a>IMAPIOfflineMgr : IMAPIOffline

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
支持注册有关用户帐户的连接状态更改的通知回调。
  
|||
|:-----|:-----|
|导出者：  <br/> |msmapi32.dll  <br/> |
|实现者：  <br/> |Outlook  <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IMAPIOfflineMgr  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[建议](imapiofflinemgr-advise.md) <br/> |注册有关连接更改的通知回调。  <br/> |
|[非企业](imapiofflinemgr-unadvise.md) <br/> |删除通知回调的给定注册。  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
| *占位符成员*  <br/> | *此成员是占位符，不受支持。*  <br/> |
   
## <a name="remarks"></a>备注

使用 **[HrOpenOfflineObj](hropenofflineobj.md)** 打开用户帐户配置文件的脱机对象后，客户端会获取支持 **IMAPIOfflineMgr** 的脱机对象。 
  
由于此接口继承自 **[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)**，客户端可以使用 **[IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)** (查询此接口 ) 以获取支持 **[IMAPIOffline 的对象](imapiofflineiunknown.md)**。 然后，客户端可以通过调用 **[IMAPIOffline：：GetCapabilities](imapioffline-getcapabilities.md)** ) 了解脱机对象 (的回调功能，并选择使用 **IMAPIOfflineMgr：：Advise** ) 设置回调 (。 
  
此接口中的大多数成员都是保留供内部使用的占位符Outlook可能会更改。 此接口的调用方只能使用记录的非占位符成员。
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline : IUnknown](imapiofflineiunknown.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)
  
[MAPI 接口](mapi-interfaces.md)

