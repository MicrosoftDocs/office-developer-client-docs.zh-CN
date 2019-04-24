---
title: IMAPIOfflineMgrAdvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr.Advise
api_type:
- COM
ms.assetid: 784b6218-548d-817a-caaa-cf9be6bc3d2f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3ca7fdc39da8d3ee8ecf6f0f253284df10a392e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321425"
---
# <a name="imapiofflinemgradvise"></a>IMAPIOfflineMgr::Advise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册客户端以接收对脱机对象的回调。
  
```cpp
HRESULT COfflineObj::Advise( 
      ULONG ulFlags, 
      MAPIOFFLINE_ADVISEINFO* pAdviseInfo, 
      ULONG* pulAdviseToken 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
>  实时修改行为的标志。 仅支持值 MAPIOFFLINE_ADVISE_DEFAULT。 
    
 _pAdviseInfo_
  
> 实时有关回调类型、何时接收回调、呼叫者的回调接口以及其他详细信息的信息。 它还包含 Outlook 在向客户端调用方发送后续通知回调时使用的客户端令牌。
    
 _pulAdviseToken_
  
> 排除向客户端调用方返回的建议令牌, 随后取消对该对象的回调。
    
## <a name="return-value"></a>返回值

S_OK
  
> 调用成功。
    
E_INVALIDARG
  
> 指定的参数无效。
    
E_NOINTERFACE
  
> *pAdviseInfo*中指定的回调接口无效。 
    
## <a name="remarks"></a>注解

使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开脱机对象时, 客户端将获得支持**IMAPIOfflineMgr**的脱机对象。 客户端可以使用**[IMAPIOffline:: GetCapabilities](imapioffline-getcapabilities.md)** 检查对象支持的回调的种类。 客户端可以确定它所需的回调的类型和其他详细信息, 然后调用**IMAPIOfflineMgr:: 建议**注册以接收有关对象的此类回调。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)


[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

