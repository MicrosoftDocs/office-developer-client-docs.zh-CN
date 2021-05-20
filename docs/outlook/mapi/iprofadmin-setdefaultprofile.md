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
  
> [in]指向将成为默认配置文件的配置文件名称的指针，或 NULL。 将  _lpszProfileName_ 设置为 NULL 指示 **SetDefaultProfile** 应删除现有的默认配置文件，使客户端没有默认配置文件。 
    
 _ulFlags_
  
> [in]控制  _lpszProfileName_ 指向的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 配置文件名称采用 Unicode 格式。 如果未MAPI_UNICODE，则配置文件名称采用 ANSI 格式。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立或删除默认配置文件。
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
## <a name="remarks"></a>备注

**IProfAdmin：：SetDefaultProfile** 方法将特定配置文件建立为客户端的默认配置文件，或清除当前的默认配置文件。 默认配置文件是在客户端开始 MAPI 会话时自动使用的配置文件。 **SetDefaultProfile** 还将新的默认配置文件PR_DEFAULT_PROFILE ( [PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 设置为 TRUE。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要使用默认配置文件启动会话，MAPI_USE_DEFAULT [MAPILogonEx](mapilogonex.md) 函数传递该标记。 
  
## <a name="see-also"></a>另请参阅



[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)
  
[MAPILogonEx](mapilogonex.md)
  
[PidTagDefaultProfile 规范属性](pidtagdefaultprofile-canonical-property.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

