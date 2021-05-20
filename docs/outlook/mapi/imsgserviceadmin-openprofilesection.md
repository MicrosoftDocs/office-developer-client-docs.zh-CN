---
title: IMsgServiceAdminOpenProfileSection
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.OpenProfileSection
api_type:
- COM
ms.assetid: 7f24910a-e14e-44a1-8477-d8968130ba74
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 32ebdea3a594b5adf5d46dc081098d3628ae145b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437110"
---
# <a name="imsgserviceadminopenprofilesection"></a>IMsgServiceAdmin::OpenProfileSection

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。 
  
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
  
> 指向标识配置文件节的 [MAPIUID](mapiuid.md) 结构的指针。 
    
 _lpInterface_
  
> [in]指向接口标识符的 (IID) 表示用于访问配置文件节的接口。 传递 NULL 会导致在  _lppProfSect_ 参数中返回指向其标准接口的指针。 配置文件部分的标准接口是 **IProfSect**。
    
 _ulFlags_
  
> [in]控制对配置文件节的访问的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许 **OpenProfileSection** 成功返回，可能在配置文件部分完全可供调用客户端使用之前。 如果配置文件部分不可用，则后续调用它可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读权限打开配置文件节，客户端不应在已授予读/写权限的假设下工作。 
    
MAPI_FORCE_ACCESS
  
> 允许访问所有配置文件节，甚至是单个服务提供商拥有的内容。
    
 _lppProfSect_
  
> [out]指向指向配置文件节的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 尝试访问呼叫者权限不足的配置文件部分。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件部分不存在。
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：OpenProfileSection** 方法打开配置文件节，即支持 [IProfSect 接口](iprofsectimapiprop.md)的对象。 配置文件部分用于从会话配置文件读取信息和将信息写入会话配置文件。 
  
 **OpenProfileSection** 不能用于打开单个服务提供商拥有的配置文件部分，除非MAPI_FORCE_ACCESS配置文件节。 
  
## <a name="notes-to-callers"></a>给调用方的说明

多个客户端可以使用只读权限打开配置文件节，但只有一个客户端可以使用读/写权限打开配置文件节。 如果另一个客户端打开了一个配置文件节，而您尝试通过调用设置了 MAPI_MODIFY 标志的 **OpenProfileSection** 来打开该节，则调用将失败，并返回 MAPI_E_NO_ACCESS。 
  
如果打开部分进行写入，则只读打开操作将失败。 
  
您可以通过调用具有 MAPI_MODIFY 标志和 _lpUID_ 参数中不存在 [的 MAPIUID](mapiuid.md)结构的 **OpenProfileSection** 来创建配置文件节。 请务必指定MAPI_MODIFY。 如果将  _lpUID_ 设置为指向不存在的 **MAPIUID，** 而将 **OpenProfileSection** 设置为使用只读的默认访问模式，则调用将失败，MAPI_E_NOT_FOUND。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |OpenProfileSection  <br/> |MFCMAPI 使用 **IMsgServiceAdmin：：OpenProfileSection** 方法打开配置文件节。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

