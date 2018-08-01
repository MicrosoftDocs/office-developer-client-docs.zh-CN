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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cd70f5ee7b58bdf0b1fd61b1056bfc77e3e35992
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775991"
---
# <a name="iprofadmincopyprofile"></a>IProfAdmin::CopyProfile

  
  
**适用于**： Outlook 
  
一个配置文件的副本。
  
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
  
> [in]一个指向要复制的配置文件的名称。
    
 _lpszOldPassword_
  
> [in]指向要复制的配置文件的密码的指针。
    
 _lpszNewProfileName_
  
> [in]一个指向复制的配置文件的新名称。
    
 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何复制配置文件。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示一个对话框，提示用户输入正确的密码的配置文件复制。 如果未设置此标志，则不显示任何对话框。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 配置文件成功复制。
    
MAPI_E_ACCESS_DENIED 
  
> 与现有的配置文件的相同的新配置文件名称。
    
MAPI_E_LOGON_FAILED 
  
> 要复制的配置文件的密码不正确，并向用户请求正确的密码，因为_ulFlags_参数中未设置 MAPI_DIALOG 无法显示一个对话框。 
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

由指向_lpszOldProfileName_，将其命名配置文件的副本所指的_lpszNewProfileName_ **IProfAdmin::CopyProfile**方法使。 将配置文件复制留副本与原始相同的密码。
  
原始的配置文件、 其密码和副本的名称的长度最多为 64 个字符，并可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。
    
- 嵌入的空格，但不是前导或尾随空格。
    
在所有操作系统上不支持配置文件密码。 在操作系统上不支持配置文件密码， _lpszOldPassword_可以为 NULL 或为零长度字符串的指针。 
  
_LpszOldPassword_设置为 NULL，如果要复制的配置文件需要密码，并设置了 MAPI_DIALOG 标志;显示一个对话框，提示用户提供密码。 如果密码是必需的但_lpszOldPassword_设置为 NULL，未设置 MAPI_DIALOG 标志**CopyProfile**返回 MAPI_E_LOGON_FAILED。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

