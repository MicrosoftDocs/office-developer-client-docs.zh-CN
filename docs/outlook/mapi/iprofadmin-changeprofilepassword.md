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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420239"
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
  
> [in]指向与要更改的密码关联的配置文件的名称的指针。
    
 _lpszOldPassword_
  
> [in]指向当前密码的指针。
    
 _lpszNewPassword_
  
> [in]指向新密码的指针。
    
 _ulFlags_
  
> [in]控制传入字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 配置文件名称和密码采用 Unicode 格式。 如果未MAPI_UNICODE，则这些字符串采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 如果调用此方法，它将返回S_OK。 但是，不会执行任何操作。
    
## <a name="remarks"></a>备注

请勿使用此方法。 MAPI 不支持配置文件的密码。
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

