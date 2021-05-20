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
  
> [in]指向要复制的配置文件的名称的指针。
    
 _lpszOldPassword_
  
> [in]指向要复制的配置文件的密码的指针。
    
 _lpszNewProfileName_
  
> [in]指向复制的配置文件的新名称的指针。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]控制配置文件复制方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示一个对话框，提示用户输入要复制的配置文件的正确密码。 如果未设置此标志，则不显示任何对话框。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制配置文件。
    
MAPI_E_ACCESS_DENIED 
  
> 新配置文件名称与现有配置文件的名称相同。
    
MAPI_E_LOGON_FAILED 
  
> 要复制的配置文件的密码不正确，并且无法向用户显示一个对话框来请求正确的密码，因为 MAPI_DIALOG  _ulFlags_ 参数中未设置该密码。 
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

**IProfAdmin：：CopyProfile** 方法创建 _lpszOldProfileName_ 指向的配置文件的副本，并指定 _lpszNewProfileName_ 指向的名称。 复制配置文件会保留副本与原始副本相同的密码。
  
原始配置文件的名称、其密码和副本的长度最多为 64 个字符，可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。
    
- 嵌入空格，但不包括前导或尾随空格。
    
配置文件密码并非在所有操作系统上都受支持。 在不支持配置文件密码的操作系统上  _，lpszOldPassword_ 可以是 NULL 或指向零长度字符串的指针。 
  
如果  _lpszOldPassword_ 设置为 NULL，则要复制的配置文件需要密码，并设置MAPI_DIALOG标记;将显示提示用户输入密码的对话框。 如果需要密码，但  _lpszOldPassword_ 设置为 NULL，并且未设置 MAPI_DIALOG 标志 **，CopyProfile** 将返回MAPI_E_LOGON_FAILED。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin : IUnknown](iprofadminiunknown.md)

