---
title: IProfAdminCopyProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.CopyProfile
api_type:
- COM
ms.assetid: f4846dc3-0236-44ed-a1b1-8c13d48fb58a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c3c4ac10003aad8949de94e0f144410af10078b1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437236"
---
# <a name="iprofadmincopyprofile"></a>IProfAdmin::CopyProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制配置文件。
  
```cpp
HRESULTCopyProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszOldProfileName_
  
> 实时指向要复制的配置文件的名称的指针。
    
 _lpszOldPassword_
  
> 实时指向要复制的配置文件的密码的指针。
    
 _lpszNewProfileName_
  
> 实时指向复制的配置文件的新名称的指针。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> 实时用于控制如何复制配置文件的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示一个对话框, 提示用户输入要复制的配置文件的正确密码。 如果未设置此标志, 则不会显示任何对话框。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制配置文件。
    
MAPI_E_ACCESS_DENIED 
  
> 新配置文件的名称与现有配置文件的名称相同。
    
MAPI_E_LOGON_FAILED 
  
> 要复制的配置文件的密码不正确, 并且无法向用户显示对话框来请求正确的密码, 因为未在_ulFlags_参数中设置 MAPI_DIALOG。 
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>说明

**IProfAdmin:: CopyProfile**方法创建由_lpszOldProfileName_指向的配置文件的副本, 并为其提供_lpszNewProfileName_指向的名称。 复制配置文件会保留副本与原始文件相同的密码。
  
原始配置文件的名称、其密码和副本的长度最高为64个字符, 并且可以包含以下字符:
  
- 所有字母数字字符, 包括重音字符和下划线字符。
    
- 嵌入空格, 但不能是前导空格或尾随空格。
    
配置文件密码在所有操作系统上均不受支持。 在不支持配置文件密码的操作系统上, _lpszOldPassword_可以是 NULL, 也可以是指向零长度字符串的指针。 
  
如果将_lpszOldPassword_设置为 NULL, 要复制的配置文件需要密码, 并且设置了 MAPI_DIALOG 标志;将显示一个对话框, 提示用户提供密码。 如果需要密码, 但_lpszOldPassword_设置为 NULL, 并且未设置 MAPI_DIALOG 标志, 则**CopyProfile**将返回 MAPI_E_LOGON_FAILED。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

