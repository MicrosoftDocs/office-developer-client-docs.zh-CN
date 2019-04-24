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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9d7c1693dfb22ae89afed8cbe1426c1e186f8b2d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329405"
---
# <a name="imapisessionopenprofilesection"></a>IMAPISession::OpenProfileSection

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。 
  
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
  
> 实时指向标识配置文件节的[MAPIUID](mapiuid.md)结构的指针。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问配置文件部分的接口。 传递 NULL 会导致_lppProfSect_参数返回指向配置文件节的标准接口**IProfSect**的指针。
    
 _ulFlags_
  
> 实时用于控制对配置文件部分的访问的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProfileSection**成功返回, 这可能在配置文件部分完全可用于调用客户端之前返回。 如果 "配置文件" 部分不可用, 则对其进行后续调用可能会导致出错。 
    
MAPI_FORCE_ACCESS
  
> 允许访问不属于提供程序的配置文件部分。
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 配置文件分区以只读权限打开, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
 _lppProfSect_
  
> 排除指向指向配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开 "配置文件" 部分。
    
MAPI_E_NO_ACCESS 
  
> 试图访问呼叫者没有足够权限的配置文件部分。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件部分不存在。
    
## <a name="remarks"></a>注解

**IMAPISession:: OpenProfileSection**方法打开一个配置文件节或支持**IProfSect**接口的对象。 配置文件节用于读取信息以及将信息写入会话配置文件。 
  
除非在_ulFlags_参数中指定 MAPI_FORCE_ACCESS, 否则, 不能使用**OpenProfileSection**打开单个服务提供程序所拥有的配置文件部分。 
  
## <a name="notes-to-callers"></a>给调用方的说明

多个客户端可以打开具有只读权限的配置文件部分, 但只有一台客户端可以打开具有读/写权限的配置文件节。 如果另一个客户端有一个配置文件节打开, 您试图通过调用**OpenProfileSection**并设置 MAPI_MODIFY 标志来打开, 则该调用将失败, 返回 MAPI_E_NO_ACCESS。 
  
如果为写入打开了该节, 则只读打开操作将失败。 
  
您可以通过在_lpUID_参数中调用带有 MAPI_MODIFY 标志的**OpenProfileSection**和不存在的**MAPIUID**结构来创建配置文件节。 确保指定 MAPI_MODIFY。 如果将_lpUID_设置为指向不存在的**MAPIUID** , 并且将**OpenProfileSection**设置为使用只读的默认访问模式, 则调用将会因 MAPI_E_NOT_FOUND 而失败。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)

