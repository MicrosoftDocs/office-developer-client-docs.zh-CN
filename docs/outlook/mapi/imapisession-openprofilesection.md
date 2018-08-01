---
title: IMAPISessionOpenProfileSection
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenProfileSection
api_type:
- COM
ms.assetid: e2757028-27e7-4fc0-9674-e8e30737ef1d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e5f329ef0d3483683d5c94ed38c6631d86e77b93
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775575"
---
# <a name="imapisessionopenprofilesection"></a>IMAPISession::OpenProfileSection

  
  
**适用于**： Outlook 
  
打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。 
  
```cpp
HRESULT OpenProfileSection(
  LPMAPIUID lpUID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPPROFSECT FAR * lppProfSect
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]指向标识配置文件部分的[MAPIUID](mapiuid.md)结构的指针。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问配置文件部分的接口的指针。 传递 NULL 会导致_lppProfSect_参数，以返回到配置文件部分的标准接口， **IProfSect**的指针。
    
 _ulFlags_
  
> [in]Flags 控制访问到配置文件部分的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProfileSection**成功返回可能之前配置文件节是完全可调用客户端。 如果配置文件部分不可用，请进行后续呼叫到它会导致错误。 
    
MAPI_FORCE_ACCESS
  
> 允许访问不属于提供程序的配置文件内容。
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下配置文件部分打开具有只读权限和客户端不应从事的读/写权限授予假设。 
    
 _lppProfSect_
  
> [输出]指向配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 尝试访问呼叫者有权限不足，无法配置文件一节。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件节不存在。
    
## <a name="remarks"></a>说明

**IMAPISession::OpenProfileSection**方法打开一个配置文件节或支持**IProfSect**接口的对象。 配置文件节用于进行读取和写入会话配置文件信息。 
  
不能使用**OpenProfileSection**打开配置文件部分自己的单个服务提供程序，除非_ulFlags_参数中指定 MAPI_FORCE_ACCESS。 
  
## <a name="notes-to-callers"></a>给调用方的说明

多个客户端可以具有只读权限，打开配置文件一节，但只有一个客户端可以具有读/写权限打开配置文件一节。 如果另一个客户端打开您尝试通过调用设置了 MAPI_MODIFY 标志**OpenProfileSection**打开配置文件一节，则调用将失败，返回 MAPI_E_NO_ACCESS。 
  
只读状态打开操作失败，如果该节为打开以进行写入。 
  
您可以通过调用不带 MAPI_MODIFY 标志和_lpUID_参数中的不存在**MAPIUID**结构**OpenProfileSection**创建配置文件一节。 确保您指定 MAPI_MODIFY。 如果设置_lpUID_以指向不存在**MAPIUID** **OpenProfileSection**设置为使用默认访问模式的只读的则调用将失败与 MAPI_E_NOT_FOUND。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

