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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f50c0eb9e3af68e206eaa5bcc51cefa923c30f72
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413176"
---
# <a name="imslogonopenstatusentry"></a>IMSLogon::OpenStatusEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开 status 对象。
  
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
  
> [in]指向要打开的状态 (IID) 接口标识符的指针。 传递 NULL 表示返回对象的标准接口 (，在这种情况下 [，IMAPIStatus](imapistatusimapiprop.md) 接口) 。 _还可以将 lpInterface_ 参数设置为对象相应接口的标识符。 
    
 _ulFlags_
  
> [in]控制状态对象的打开方式的标志的位掩码。 可以设置以下标志：
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，使用只读权限创建对象，客户端应用程序不应在已授予读/写权限的假设下工作。 
    
 _lpulObjType_
  
> [out]指向已打开对象的类型的指针。
    
 _lppEntry_
  
> [out]指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

消息存储提供程序实现 **IMSLogon：：OpenStatusEntry** 方法以打开状态对象。 然后，此状态对象用于使客户端能够调用 [IMAPIStatus](imapistatusimapiprop.md) 方法。 例如，客户端可以使用 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 方法重新配置邮件存储登录会话，或者使用 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法验证邮件存储登录会话的状态。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)
  
[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

