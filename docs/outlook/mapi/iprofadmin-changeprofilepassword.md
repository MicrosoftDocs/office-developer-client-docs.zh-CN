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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 41066d4418760a676fbc02241bfc12d83275da9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572996"
---
# <a name="iprofadminchangeprofilepassword"></a>IProfAdmin::ChangeProfilePassword

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]一个指向相关联的密码更改配置文件的名称。
    
 _lpszOldPassword_
  
> [in]一个指向当前密码。
    
 _lpszNewPassword_
  
> [in]一个指向新密码。
    
 _ulFlags_
  
> [in]位掩码的标志的控制传入的字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 配置文件的名称和密码的 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 如果调用此方法，则它将返回 S_OK。 但是，不会执行任何操作。
    
## <a name="remarks"></a>注解

不要使用此方法。 MAPI 不支持的配置文件的密码。
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

