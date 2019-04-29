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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 44be43864d943257520f27297e5754a4978c568d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439623"
---
# <a name="iprofadminsetdefaultprofile"></a>IProfAdmin::SetDefaultProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
设置或清除客户端的默认配置文件。
  
```cpp
HRESULT SetDefaultProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> 实时指向将成为默认值的配置文件的名称的指针或 NULL。 将_lpszProfileName_设置为 NULL 表示**SetDefaultProfile**应删除现有的默认配置文件, 使客户端不使用默认配置。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制由_lpszProfileName_指向的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 配置文件名称为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则配置文件名称将采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立或删除了默认配置文件。
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
## <a name="remarks"></a>说明

**IProfAdmin:: SetDefaultProfile**方法要么将特定配置文件建立为客户端的默认配置文件, 要么清除当前的默认配置文件。 默认配置文件是在客户端开始 MAPI 会话时自动使用的配置文件。 **SetDefaultProfile**还将新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性设置为 TRUE。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要使用默认配置文件启动会话, 请将 MAPI_USE_DEFAULT 标志传递给[MAPILogonEx](mapilogonex.md)函数。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)
  
[MAPILogonEx](mapilogonex.md)
  
[PidTagDefaultProfile 规范属性](pidtagdefaultprofile-canonical-property.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

