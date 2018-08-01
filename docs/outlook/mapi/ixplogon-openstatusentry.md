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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0e96c0b99f0a5f7511ed59b483ab9409eafad882
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776118"
---
# <a name="ixplogonopenstatusentry"></a>IXPLogon::OpenStatusEntry

  
  
**适用于**： Outlook 
  
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
  
> [in]指向传输登录对象的界面标识符 (IID) 的指针。 如果传递 NULL 返回[IMAPIStatus](imapistatusimapiprop.md)接口。 _LpInterface_参数还可以设置为对象的接口的标识符。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开状态对象。 可以设置以下标记：
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认接口是只读的。 
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppEntry_
  
> [输出]指向打开的状态对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>说明

客户端应用程序的传输提供程序的状态表格行中的项标识符调用**OpenEntry**方法时，MAPI 后台处理程序调用**IXPLogon::OpenStatusEntry**方法。 **OpenStatusEntry**打开与此特定传输提供程序的登录关联的**IMAPIStatus**接口的对象。 此对象然后用于启用客户端应用程序调用**IMAPIStatus**方法 （例如，若要重新登录会话配置使用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法，或使用[验证登录会话的状态IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法)。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

