---
title: IMSLogonOpenStatusEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.OpenStatusEntry
api_type:
- COM
ms.assetid: 850e256b-6b50-428c-aede-287edaf7b005
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 55cf41d251db4c84dad9f12d8f83d0b0dda63ff3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775912"
---
# <a name="imslogonopenstatusentry"></a>IMSLogon::OpenStatusEntry

  
  
**适用于**： Outlook 
  
打开状态对象。
  
```cpp
HRESULT OpenStatusEntry(
  LPCIID lpInterface,
  ULONG ulFlags,
  ULONG FAR * lpulObjType,
  LPVOID FAR * lppEntry
);
```

## <a name="parameters"></a>参数

 _lpInterface_
  
> [in]指向要打开的状态对象的界面标识符 (IID) 的指针。 传递 NULL 指示对象的标准接口返回 （在本例中为[IMAPIStatus](imapistatusimapiprop.md)接口）。 _LpInterface_参数还可以设置为适当的接口的对象的标识符。 
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开状态对象。 可以设置以下标记：
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象在创建具有只读权限，并以为，读/写权限授予客户端应用程序不起作用。 
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppEntry_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

消息存储提供程序实现**IMSLogon::OpenStatusEntry**方法打开状态对象。 此状态对象然后用于启用客户端调用[IMAPIStatus](imapistatusimapiprop.md)方法。 例如，客户端可以使用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法重新配置消息存储登录会话或[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法以验证邮件存储登录会话的状态。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)
  
[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

