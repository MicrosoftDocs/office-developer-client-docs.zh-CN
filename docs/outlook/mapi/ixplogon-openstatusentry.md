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
  
打开传输提供程序的状态对象。
  
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
  
> [in]指向用于传输登录 (IID) 接口标识符的指针。 传递 NULL 将返回 [IMAPIStatus](imapistatusimapiprop.md) 接口。 _lpInterface_ 参数还可以设置为对象的接口的标识符。 
    
 _ulFlags_
  
> [in]控制状态对象的打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认接口是只读的。 
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppEntry_
  
> [out]指向已打开状态对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

当客户端应用程序调用传输提供程序状态表行中的条目标识符的 **OpenEntry** 方法时，MAPI 后台处理程序将调用 **IXPLogon：：OpenStatusEntry** 方法。 **OpenStatusEntry** 打开一个对象，该对象具有与此特定传输提供程序登录相关联的 **IMAPIStatus** 接口。 然后，使用此对象使客户端应用程序能够调用 **IMAPIStatus** 方法 (例如，使用 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法重新配置登录会话，或者使用 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法) 验证登录会话的状态。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

