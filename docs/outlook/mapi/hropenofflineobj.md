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
ms.openlocfilehash: cc71974d841005785932cc9017d44c3c0614687d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563385"
---
# <a name="hropenofflineobj"></a>HrOpenOfflineObj

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开基于给定配置文件的脱机对象。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|导出：  <br/> |msmapi32.dll  <br/> |
|调用：  <br/> |客户端  <br/> |
|通过实现：  <br/> |Outlook  <br/> |
   
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
  
> [in]不使用此参数。 它必须是 0。
    
 _pwszProfileNameIn_
  
> [in]脱机对象为配置文件的名称。 它必须在 Unicode 中表示。 
    
 _pGUID_
  
> [in]为 GUID 可用于唯一标识此对象从其他脱机对象的指针。 它必须是**GUID_GlobalState**。
    
 _保留_
  
> [in]不使用此参数。 它必须是**null**。
    
 _ppOfflineObj_
  
> [输出]指向所需的脱机对象的指针。 呼叫者可以使用此指针访问[IMAPIOfflineMgr: IMAPIOffline](imapiofflinemgrimapioffline.md)找到此对象支持的回调并为其设置回调的接口。 
    
## <a name="return-values"></a>返回值

S_OK 
  
- 成功函数调用。
    
MAPI_E_NOT_FOUND
  
- 函数调用失败。
    
## <a name="remarks"></a>注解

这是客户端发出时在客户端需要的任何给定配置文件的连接状态更改通知的第一个呼叫。 时调用**HrOpenOfflineObj**，客户端获取脱机支持**IMAPIOfflineMgr**的对象。 客户端可以检查回调对象 （通过使用[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)） 支持的类型，然后设置回调 （通过使用[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)）。
  
当使用[GetProcAddress](http://msdn.microsoft.com/en-us/library/ms683212.aspx)查找 msmapi32.dll 中此函数的地址，指定**HrOpenOfflineObj@20**作为过程名称。 
  
 **HrOpenOfflineObj**仅适用于客户端的 COM 加载项，并在 Outlook 进程内运行的 Exchange 客户端扩展 MAPI 提供程序。 否则， **HrOpenOfflineObj**返回**MAPI_E_NOT_FOUND**。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline : IUnknown](imapiofflineiunknown.md)
  
[IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md)


[关于脱机状态 API](about-the-offline-state-api.md)
  
[MAPI 常量](mapi-constants.md)

