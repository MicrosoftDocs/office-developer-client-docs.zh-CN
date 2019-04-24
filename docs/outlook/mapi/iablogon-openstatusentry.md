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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 22f98e52444b17c383737bffd1685df0fb7ba8bb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349019"
---
# <a name="iablogonopenstatusentry"></a>IABLogon::OpenStatusEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开提供程序的 status 对象。
  
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
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示必须用于访问 status 对象的接口。 传递 NULL 将返回对象的标准接口[IMAPIStatus: IMAPIProp](imapistatusimapiprop.md)。
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制状态对象的打开方式。 可以设置以下标志:
    
MAPI_MODIFY 
  
> 请求读取/写入权限。 默认情况下, 将使用只读访问权限打开对象, 并且调用方不应假定已授予读/写权限。
    
 _lpulObjType_
  
> 排除一个指针, 指向打开的对象的类型。
    
 _lppEntry_
  
> 排除指向打开的对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 状态对象已打开。
    
## <a name="remarks"></a>注解

通讯簿提供程序实现**OpenStatusEntry**方法, 以授予对其状态对象的访问权限。 所有通讯簿提供程序都需要实现一个 status 对象, 该对象至少支持[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法。 有关详细信息, 请参阅[Status Object 实现](status-object-implementation.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)
  
[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)
  
[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IABLogon : IUnknown](iablogoniunknown.md)

