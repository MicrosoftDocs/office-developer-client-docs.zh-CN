---
title: IProfAdminSetDefaultProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.SetDefaultProfile
api_type:
- COM
ms.assetid: 58f50535-b0ed-4097-bda8-fd3ccc2d4b49
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cf5060ba2113032fe1e13e5417590006808a53e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776006"
---
# <a name="iprofadminsetdefaultprofile"></a>IProfAdmin::SetDefaultProfile

  
  
**适用于**： Outlook 
  
设置或清除客户端的默认配置文件。
  
```cpp
HRESULT SetDefaultProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> [in]一个指向将成为默认值，则为 NULL 的配置文件的名称。 将_lpszProfileName_设置为 NULL 指示**SetDefaultProfile**应删除现有的默认配置文件，而客户端无默认值。 
    
 _ulFlags_
  
> [in]由_lpszProfileName_指向控制字符串的类型的标志位掩码。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 配置文件名称为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，是 ANSI 格式的配置文件名称。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 默认配置文件成功建立或删除。
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
## <a name="remarks"></a>说明

**IProfAdmin::SetDefaultProfile**方法建立为客户端的默认配置文件的特定配置文件，或清除当前的默认配置文件。 默认配置文件是客户端开始 MAPI 会话时，系统将自动使用的配置文件。 **SetDefaultProfile**还将该新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性设置为 TRUE。
  
## <a name="notes-to-callers"></a>给调用方的说明

要使用的默认配置文件启动会话，传递给[MAPILogonEx](mapilogonex.md)函数 MAPI_USE_DEFAULT 标志。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)
  
[MAPILogonEx](mapilogonex.md)
  
[PidTagDefaultProfile 规范属性](pidtagdefaultprofile-canonical-property.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

