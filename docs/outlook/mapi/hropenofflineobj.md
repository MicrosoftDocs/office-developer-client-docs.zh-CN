---
title: HrOpenOfflineObj
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrOpenOfflineObj
api_type:
- HeaderDef
ms.assetid: cee1a940-fe01-d364-5d7c-c9e9dfeb8979
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ef929bf778fabc4350f553d185838dd5cb2cf0b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347745"
---
# <a name="hropenofflineobj"></a>HrOpenOfflineObj

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开基于给定配置文件的脱机对象。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出者：  <br/> |msmapi32.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |
   
```cpp
typedef HRESULT (STDMETHODCALLTYPE HROPENOFFLINEOBJ)( 
      ULONG ulReserved, 
      LPCWSTR pwszProfileNameIn, 
      const GUID* pGUID, 
      const GUID* pReserved, 
      IMAPIOfflineMgr** ppOfflineObj); 

```

## <a name="parameters"></a>参数

 _ulReserved_
  
> [in]此参数未使用。 它必须是 0。
    
 _pwszProfileNameIn_
  
> [in]脱机对象所针对的配置文件的名称。 它必须用 Unicode 表示。 
    
 _pGUID_
  
> [in]指向可用于从其他脱机对象唯一标识此对象的 GUID 的指针。 它必须是 **GUID_GlobalState**。
    
 _pReserved_
  
> [in]此参数未使用。 它必须为 **null**。
    
 _ppOfflineObj_
  
> [out]指向请求的脱机对象的指针。 调用方可以使用此指针访问 [IMAPIOfflineMgr ： IMAPIOffline](imapiofflinemgrimapioffline.md) 接口，以查找此对象支持的回调并设置其回调。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 函数调用成功。
    
MAPI_E_NOT_FOUND
  
- 函数调用失败。
    
## <a name="remarks"></a>备注

这是客户端在客户端希望收到给定配置文件的任何连接状态更改通知时进行的第一个调用。 调用 **HrOpenOfflineObj** 时，客户端获取支持 **IMAPIOfflineMgr** 的脱机对象。 客户端可以使用 [IMAPIOffline：：GetCapabilities](imapioffline-getcapabilities.md)) 检查对象 (支持的回调类型，然后使用 [IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)) 为 (设置回调。
  
使用 [GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx) 在 msmapi32.dll 中查找此函数的地址时，HrOpenOfflineObj@20 **指定为过程** 名称。 
  
 **HrOpenOfflineObj** 仅适用于 MAPI 提供程序、COM 加载项和 Exchange 进程内运行的客户端扩展Outlook客户端。 否则 **，HrOpenOfflineObj 将** 返回 **MAPI_E_NOT_FOUND**。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline : IUnknown](imapiofflineiunknown.md)
  
[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)

