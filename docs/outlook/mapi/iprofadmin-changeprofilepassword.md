---
title: IProfAdminChangeProfilePassword
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.ChangeProfilePassword
api_type:
- COM
ms.assetid: a41f707a-5c84-49aa-aeb6-469b2600e181
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c7124c8e3f2ced66d303321ff7aee8592a723a2b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317120"
---
# <a name="iprofadminchangeprofilepassword"></a>IProfAdmin::ChangeProfilePassword

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
已弃用。 更改配置文件的密码。
  
```cpp
HRESULT ChangeProfilePassword(
  LPSTR lpszProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewPassword,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> 实时一个指针, 指向与要更改的密码关联的配置文件的名称。
    
 _lpszOldPassword_
  
> 实时指向当前密码的指针。
    
 _lpszNewPassword_
  
> 实时指向新密码的指针。
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制传入的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 配置文件名称和密码采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 如果调用此方法, 它将返回 S_OK。 但是, 不会执行任何操作。
    
## <a name="remarks"></a>注解

请勿使用此方法。 MAPI 不支持配置文件的密码。
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

