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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317389"
---
# <a name="imsgserviceadminopenprofilesection"></a>IMsgServiceAdmin::OpenProfileSection

  
  
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
  
> 指向标识配置文件节的[MAPIUID](mapiuid.md)结构的指针。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问配置文件部分的接口。 将 NULL 结果传递到在_lppProfSect_参数中返回到其标准接口的指针。 配置文件节的标准接口是**IProfSect**。
    
 _ulFlags_
  
> 实时用于控制对配置文件部分的访问的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFERRED_ERRORS 
  
> 允许**OpenProfileSection**成功返回, 这可能在配置文件部分完全可用于调用客户端之前返回。 如果 "配置文件" 部分不可用, 则对其进行后续调用可能会引发错误。 
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 配置文件分区以只读权限打开, 并且客户端不应在假定已授予读/写权限时才起作用。 
    
MAPI_FORCE_ACCESS
  
> 允许访问所有配置文件部分, 甚至包括各个服务提供商拥有的部分。
    
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

**IMsgServiceAdmin:: OpenProfileSection**方法打开一个 profile 部分, 该对象支持[IProfSect](iprofsectimapiprop.md)接口。 配置文件节用于读取信息以及将信息写入会话配置文件。 
  
 **OpenProfileSection**不能用于打开由单个服务提供商拥有的配置文件节, 除非使用 MAPI_FORCE_ACCESS。 
  
## <a name="notes-to-callers"></a>给调用方的说明

多个客户端可以打开具有只读权限的配置文件部分, 但只有一台客户端可以打开具有读/写权限的配置文件节。 如果另一个客户端有一个配置文件节打开, 您试图通过调用**OpenProfileSection**并设置 MAPI_MODIFY 标志来打开, 则该调用将失败, 返回 MAPI_E_NO_ACCESS。 
  
如果为写入打开了该节, 则只读打开操作将失败。 
  
您可以通过在_lpUID_参数中调用带有 MAPI_MODIFY 标志的**OpenProfileSection**和不存在的[MAPIUID](mapiuid.md)结构来创建配置文件节。 确保指定 MAPI_MODIFY。 如果将_lpUID_设置为指向不存在的**MAPIUID** , 并且将**OpenProfileSection**设置为使用只读的默认访问模式, 则调用将会因 MAPI_E_NOT_FOUND 而失败。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions  <br/> |OpenProfileSection  <br/> |MFCMAPI 使用**IMsgServiceAdmin:: OpenProfileSection**方法打开配置文件部分。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)
  
[IProfSect : IMAPIProp](iprofsectimapiprop.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

