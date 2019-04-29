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
  
打开一个 status 对象。
  
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
  
> 实时指向要打开的 status 对象的接口标识符 (IID) 的指针。 传递 NULL 表示返回对象的标准接口 (在此示例中为[IMAPIStatus](imapistatusimapiprop.md)接口)。 也可以将_lpInterface_参数设置为对象的相应接口的标识符。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制状态对象的打开方式。 可以设置以下标志:
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 创建具有只读权限的对象, 并且客户端应用程序不应在假定已授予读/写权限时才起作用。 
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppEntry_
  
> 排除指向指向已打开对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

邮件存储提供程序实现**IMSLogon:: OpenStatusEntry**方法以打开 status 对象。 此状态对象随后用于使客户端可以调用[IMAPIStatus](imapistatusimapiprop.md)方法。 例如, 客户端可以使用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法重新配置邮件存储登录会话或[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法以验证邮件存储登录会话的状态。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)
  
[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IMSLogon : IUnknown](imslogoniunknown.md)

