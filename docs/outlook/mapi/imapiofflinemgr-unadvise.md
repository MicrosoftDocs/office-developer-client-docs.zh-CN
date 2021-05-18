---
title: IMAPIOfflineMgrUnadvise
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr.Unadvise
api_type:
- COM
ms.assetid: 250b9137-facb-81a2-41b1-96a57366c04e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 800f79179f999ba193d4177abb7341095b8b896d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404853"
---
# <a name="imapiofflinemgrunadvise"></a>IMAPIOfflineMgr::Unadvise

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
取消脱机对象的回调。
  
```cpp
HRESULT COfflineObj::Unadvise( 
      ULONG ulFlags, 
      ULONG ulAdviseToken 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]用于取消回调的标志。 仅支持MAPIOFFLINE_UNADVISE_DEFAULT值。
    
 _ulAdviseToken_
  
> [in]建议令牌，用于标识要取消的回调注册。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 呼叫成功。 此调用必须返回S_OK。
    
## <a name="remarks"></a>备注

删除与从对 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** 的先前调用返回的 *ulAdviseToken* 关联的回调的注册。 使 **IMAPIOfflineMgr** 对象释放对与 *ulAdviseToken* 关联的 **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 对象的引用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)


[MAPI 常量](mapi-constants.md)

