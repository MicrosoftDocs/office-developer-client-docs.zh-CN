---
title: IProfAdminRenameProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.RenameProfile
api_type:
- COM
ms.assetid: 2a575cac-dbfd-4f42-9c10-4b7e355a065e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 162f20485fc21cf8523b6d4a653e52c35f4b3d9a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317078"
---
# <a name="iprofadminrenameprofile"></a>IProfAdmin::RenameProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
为配置文件分配一个新名称。
  
```cpp
HRESULT RenameProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszOldProfileName_
  
> 实时指向要重命名的配置文件的当前名称的指针。
    
 _lpszOldPassword_
  
> 实时始终为 NULL。
    
 _lpszNewProfileName_
  
> 实时指向要重命名的配置文件的新名称的指针。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _ulFlags_
  
> 实时始终为 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功重命名配置文件。
    
MAPI_E_LOGON_FAILED 
  
> 配置文件密码不正确。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

**IProfAdmin:: RenameProfile**方法将新名称分配给配置文件 (如果有的话)。 如果调用**RenameProfile**时, 客户端正在使用重命名的配置文件, **RenameProfile**将标记配置文件并返回 S_OK, 而不是在配置文件正在使用时尝试重命名操作。 不再使用该配置文件时, **RenameProfile**会为其分配新名称。 
  
配置文件的旧名称和新名称的长度最高为64个字符, 并且可以包含以下字符:
  
- 所有字母数字字符, 包括重音字符和下划线字符。
    
- 嵌入空格, 但不能是前导空格或尾随空格。
    
_lpszPassword_应始终为 NULL 或指向零长度字符串的指针。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

