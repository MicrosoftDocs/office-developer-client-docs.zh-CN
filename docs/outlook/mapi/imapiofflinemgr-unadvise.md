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
  
取消对脱机对象的回调。
  
```cpp
HRESULT COfflineObj::Unadvise( 
      ULONG ulFlags, 
      ULONG ulAdviseToken 
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于取消回调的标志。 仅支持值 MAPIOFFLINE_UNADVISE_DEFAULT。
    
 _ulAdviseToken_
  
> 实时一个建议令牌, 用于标识要取消的回调注册。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 调用成功。 此调用必须返回 S_OK。
    
## <a name="remarks"></a>说明

删除与*ulAdviseToken*相关联的回调的注册, 该回调是从以前对**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 的调用返回的。 使**IMAPIOfflineMgr**对象释放其对与*ulAdviseToken*相关联的**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)** 对象的引用。 
  
## <a name="see-also"></a>另请参阅



[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)


[MAPI 常量](mapi-constants.md)

