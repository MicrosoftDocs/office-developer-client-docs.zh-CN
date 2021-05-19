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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419518"
---
# <a name="iprofadminrenameprofile"></a>IProfAdmin::RenameProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
向配置文件分配新名称。
  
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
  
> [in]指向要重命名的配置文件的当前名称的指针。
    
 _lpszOldPassword_
  
> [in]始终为 NULL。
    
 _lpszNewProfileName_
  
> [in]指向要重命名的配置文件的新名称的指针。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 
    
 _ulFlags_
  
> [in]始终为 NULL。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 配置文件已成功重命名。
    
MAPI_E_LOGON_FAILED 
  
> 配置文件密码不正确。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

**IProfAdmin：：RenameProfile** 方法为配置文件分配一个新名称（如果有）。 如果在调用 **RenameProfile** 时要重命名的配置文件正由客户端使用 **，RenameProfile** 将标记该配置文件并返回 S_OK 而不是在使用配置文件时尝试重命名操作。 当配置文件不再使用时 **，RenameProfile** 会为其分配新名称。 
  
配置文件的旧名称和新名称的长度最多为 64 个字符，可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。
    
- 嵌入空格，但不包括前导或尾随空格。
    
_lpszPassword_ 应始终为 NULL 或指向零长度字符串的指针。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

