---
title: IMsgServiceAdminAdminProviders
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.AdminProviders
api_type:
- COM
ms.assetid: 0d605e2c-10db-46e1-95d5-12fabd524baa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b03245d7af4c6fb3879e597d8345e5d9888e164
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567207"
---
# <a name="imsgserviceadminadminproviders"></a>IMsgServiceAdmin::AdminProviders

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回提供访问提供程序管理对象的指针。
  
```cpp
HRESULT AdminProviders(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPPROVIDERADMIN FAR * lppProviderAdmin
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要从中要管理的消息服务的唯一标识符。 
    
 _ulFlags_
  
> [in]始终为 NULL。 
    
 _lppProviderAdmin_
  
> [输出]指向提供程序的管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的提供程序的管理对象。
    
MAPI_E_NOT_FOUND 
  
> **MAPIUID**由_lpUID_指向不存在。 
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::AdminProviders**方法提供对提供程序的管理对象访问。 提供程序管理是对象支持[IProviderAdmin](iprovideradminiunknown.md)接口，使客户端执行以下操作： 
  
- 添加到消息服务的服务提供商。
    
- 删除消息服务的服务提供商。
    
- 打开配置文件部分。
    
- 访问邮件服务提供程序表。
    
在使用配置文件时可以实际的消息服务对做的更改的类型取决于邮件服务。 但是，大多数消息服务不支持更改如添加和删除提供程序配置文件时使用。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要管理的消息服务的**MAPIUID**结构，请从邮件服务表中的消息服务的行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。 有关详细信息，请参阅[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg::OnDisplayItem  <br/> |MFCMAPI 使用**IMsgServiceAdmin::AdminProviders**方法打开服务提供程序管理对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IProviderAdmin : IUnknown](iprovideradminiunknown.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

