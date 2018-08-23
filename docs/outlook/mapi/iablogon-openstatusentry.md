---
title: IABLogonOpenStatusEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.OpenStatusEntry
api_type:
- COM
ms.assetid: 66f1e246-a67a-4f8a-ae3a-6a8ec8c2b367
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cb9a2ba72ee9fd9c45aefe9d0797930a4871404a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579282"
---
# <a name="iablogonopenstatusentry"></a>IABLogon::OpenStatusEntry

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
打开提供程序的状态对象。
  
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
  
> [in]指向接口标识 (IID) 表示必须用于访问状态对象的接口的指针。 如果传递 NULL 返回对象的标准接口， [IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何打开状态对象。 可以设置以下标记：
    
MAPI_MODIFY 
  
> 请求读/写权限。 默认情况下，对象打开具有只读访问权限和呼叫者不应假定已被授予读/写权限。
    
 _lpulObjType_
  
> [输出]一个指向打开的对象的类型。
    
 _lppEntry_
  
> [输出]指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功，并已打开状态对象。
    
## <a name="remarks"></a>注解

通讯簿提供程序实现**OpenStatusEntry**方法向其状态对象授予访问权限。 所有通讯簿提供程序所都需实现支持，最少， [IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法状态对象。 有关详细信息，请参阅[状态对象实现](status-object-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)
  
[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

