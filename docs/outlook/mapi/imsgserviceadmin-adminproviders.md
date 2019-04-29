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
ms.openlocfilehash: 6b7360995a781824b50ff02b5d2dec8e481e7ba7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422759"
---
# <a name="imsgserviceadminadminproviders"></a>IMsgServiceAdmin::AdminProviders

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个指针, 该指针提供对提供程序管理对象的访问权限。
  
```cpp
HRESULT AdminProviders(
  LPMAPIUID lpUID,
  ULONG ulFlags,
  LPPROVIDERADMIN FAR * lppProviderAdmin
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> 实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要管理的邮件服务的唯一标识符。 
    
 _ulFlags_
  
> 实时始终为 NULL。 
    
 _lppProviderAdmin_
  
> 排除指向提供程序管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回提供程序管理对象。
    
MAPI_E_NOT_FOUND 
  
> _lpUID_指向的**MAPIUID**不存在。 
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin:: AdminProviders**方法提供对提供程序管理对象的访问权限。 提供程序管理是一个支持[IProviderAdmin](iprovideradminiunknown.md)接口的对象, 它允许客户端执行以下操作: 
  
- 将服务提供程序添加到邮件服务。
    
- 从邮件服务中删除服务提供程序。
    
- 打开配置文件节。
    
- 访问邮件服务提供程序表。
    
在使用配置文件时, 实际可以对邮件服务进行的更改类型取决于邮件服务。 但是, 大多数邮件服务不支持在配置文件正在使用时添加和删除提供程序等更改。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要管理的邮件服务的**MAPIUID**结构, 请从邮件服务表中的邮件服务行检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。 有关详细信息, 请参阅[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgServiceTableDlg  <br/> |CMsgServiceTableDlg:: OnDisplayItem  <br/> |MFCMAPI 使用**IMsgServiceAdmin:: AdminProviders**方法打开服务的提供程序管理对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IProviderAdmin : IUnknown](iprovideradminiunknown.md)
  
[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

