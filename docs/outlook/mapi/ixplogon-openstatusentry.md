---
title: IXPLogonOpenStatusEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.OpenStatusEntry
api_type:
- COM
ms.assetid: 261d5f7c-bb61-4e1d-aa41-cca224c63f8e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d9e09de1064a0ae034bb3618f0e5b3719a82c163
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435899"
---
# <a name="ixplogonopenstatusentry"></a>IXPLogon::OpenStatusEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开传输提供程序的 status 对象。
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPMAPISTATUS FAR * lppEntry
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> 实时指向传输登录对象的接口标识符 (IID) 的指针。 传递 NULL 将返回[IMAPIStatus](imapistatusimapiprop.md)接口。 也可以将_lpInterface_参数设置为对象接口的标识符。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制状态对象的打开方式。 可以设置以下标志:
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认接口是只读的。 
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppEntry_
  
> 排除指向打开的状态对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>说明

当客户端应用程序在传输提供程序的状态表行中为条目标识符调用**OpenEntry**方法时, MAPI 后台处理程序将调用**IXPLogon:: OpenStatusEntry**方法。 **OpenStatusEntry**将打开一个对象, 其中包含与此特定传输提供程序登录相关联的**IMAPIStatus**接口。 然后, 使用此对象来启用客户端应用程序, 以调用**IMAPIStatus**方法 (例如, 使用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法重新配置登录会话, 或使用[验证登录会话的状态。IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法)。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

