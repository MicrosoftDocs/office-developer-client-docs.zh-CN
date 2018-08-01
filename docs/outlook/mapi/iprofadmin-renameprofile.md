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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c94c60cf9ff1adbe2b54bd85b228e21b4be0e6e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776002"
---
# <a name="iprofadminrenameprofile"></a>IProfAdmin::RenameProfile

  
  
**适用于**： Outlook 
  
向一个配置文件分配一个新名称。
  
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
  
> [in]一个指向当前重命名的配置文件的名称。
    
 _lpszOldPassword_
  
> [in]始终为 NULL。
    
 _lpszNewProfileName_
  
> [in]一个指向重命名的配置文件的新名称。
    
 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。 
    
 _ulFlags_
  
> [in]始终为 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功重命名配置文件。
    
MAPI_E_LOGON_FAILED 
  
> 配置文件密码不正确。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

如果有的话， **IProfAdmin::RenameProfile**方法向一个配置文件指定一个新名称。 如果要重命名的配置文件，使用客户端调用**RenameProfile**时**RenameProfile**标记配置文件，并返回 S_OK 而不是使用配置文件时，尝试重命名操作。 不再使用配置文件时， **RenameProfile**将其分配的新名称。 
  
旧的和新的配置文件的名称可以是最多为 64 个字符的长度，并且可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。
    
- 嵌入的空格，但不是前导或尾随空格。
    
_LpszPassword_应始终为 NULL 或为零长度字符串的指针。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

