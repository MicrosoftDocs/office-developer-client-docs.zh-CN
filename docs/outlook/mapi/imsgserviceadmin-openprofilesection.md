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
ms.openlocfilehash: 8dfa777480af48819e5357fad9b1e7524148a8b7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568810"
---
# <a name="imsgserviceadminopenprofilesection"></a>IMsgServiceAdmin::OpenProfileSection

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> 指向标识配置文件部分的[MAPIUID](mapiuid.md)结构的指针。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问配置文件部分的接口的指针。 传递 NULL 将导致指向_lppProfSect_参数中要返回其标准接口的指针。 配置文件节的标准接口是**IProfSect**。
    
 _ulFlags_
  
> [in]Flags 控制访问到配置文件部分的位掩码。 可以设置以下标志：
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProfileSection**成功返回可能之前配置文件节是完全可调用客户端。 如果配置文件部分不可用，进行后续呼叫到它会引发错误。 
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下配置文件部分打开具有只读权限和客户端不应从事的读/写权限授予假设。 
    
MAPI_FORCE_ACCESS
  
> 允许对所有配置文件节，即使他们拥有单独的服务提供程序的访问。
    
 _lppProfSect_
  
> [输出]指向配置文件部分的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功打开配置文件部分。
    
MAPI_E_NO_ACCESS 
  
> 尝试访问呼叫者有权限不足，无法配置文件一节。
    
MAPI_E_NOT_FOUND 
  
> 请求的配置文件节不存在。
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::OpenProfileSection**方法打开配置文件节，支持[IProfSect](iprofsectimapiprop.md)接口的对象。 配置文件节用于进行读取和写入会话配置文件信息。 
  
 **OpenProfileSection**不能用于打开归单个服务提供程序，除非使用 MAPI_FORCE_ACCESS 的配置文件部分。 
  
## <a name="notes-to-callers"></a>给调用方的说明

多个客户端可以具有只读权限，打开配置文件一节，但只有一个客户端可以具有读/写权限打开配置文件一节。 如果另一个客户端打开您尝试通过调用设置了 MAPI_MODIFY 标志**OpenProfileSection**打开配置文件一节，则调用将失败，返回 MAPI_E_NO_ACCESS。 
  
只读状态打开操作失败，如果该节为打开以进行写入。 
  
您可以通过调用不带 MAPI_MODIFY 标志和_lpUID_参数中的不存在[MAPIUID](mapiuid.md)结构**OpenProfileSection**创建配置文件一节。 确保您指定 MAPI_MODIFY。 如果设置_lpUID_以指向不存在**MAPIUID** **OpenProfileSection**设置为使用默认访问模式的只读的则调用将失败与 MAPI_E_NOT_FOUND。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |OpenProfileSection  <br/> |MFCMAPI 使用**IMsgServiceAdmin::OpenProfileSection**方法打开配置文件一节。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

