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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 53fa6bd49190bb88daeb0438dc0112e34322383e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775494"
---
# <a name="imapiofflinemgradvise"></a>IMAPIOfflineMgr::Advise

  
  
**适用于**： Outlook 
  
注册接收回调脱机对象上的客户端。
  
```cpp
HRESULT COfflineObj::Advise( 
      ULONG ulFlags, 
      MAPIOFFLINE_ADVISEINFO* pAdviseInfo, 
      ULONG* pulAdviseToken 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
>  [in]修改行为的标志。 支持仅值 MAPIOFFLINE_ADVISE_DEFAULT。 
    
 _pAdviseInfo_
  
> [in]信息的类型回调，何时接收回调、 回调接口将呼叫者和其他详细信息。 它还包含在向客户端呼叫者发送后续的通知回调中使用 Outlook 客户端令牌。
    
 _pulAdviseToken_
  
> [输出]随后取消回调对象返回到客户端呼叫者 advise 令牌。
    
## <a name="return-value"></a>返回值

S_OK
  
> 呼叫成功。
    
E_INVALIDARG
  
> 已指定了无效的参数。
    
E_NOINTERFACE
  
> *PAdviseInfo*中指定的回调接口无效。 
    
## <a name="remarks"></a>说明

在打开时使用**[HrOpenOfflineObj](hropenofflineobj.md)** 脱机对象，客户端获取脱机支持**IMAPIOfflineMgr**的对象。 客户端可以检查回调对象使用**[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)** 支持的类型。 类型以及其他有关回调其想，，然后调用**IMAPIOfflineMgr::Advise**进行注册，以接收此类回调有关对象的详细信息，可以确定客户端。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)


[MAPI 常量](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)

