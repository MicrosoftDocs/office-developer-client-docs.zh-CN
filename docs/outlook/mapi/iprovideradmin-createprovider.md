---
title: IProviderAdminCreateProvider
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin.CreateProvider
api_type:
- COM
ms.assetid: 80c1449a-6cd9-4b93-a300-395979894b71
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 01cc8a8a54137b72091abab3671c08b526ef9e31
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776041"
---
# <a name="iprovideradmincreateprovider"></a>IProviderAdmin::CreateProvider

**适用于**： Outlook 
  
向消息服务的服务提供商。 
  
```cpp
HRESULT CreateProvider(
  LPSTR lpszProvider,
  ULONG cValues,
  LPSPropValue lpProps,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  MAPIUID FAR * lpUID
);
```

## <a name="parameters"></a>参数

 _lpszProvider_
  
> [in]一个指向要添加的提供程序的名称。
    
 _cValues_
  
> [in]_LpProps_参数指向的属性值的计数。 
    
 _lpProps_
  
> [in]一个指向介绍要添加的提供程序的属性的属性值数组。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 如果 MAPI_DIALOG 标志设置_ulFlags_参数中，使用_ulUIParam_参数。 
    
 _ulFlags_
  
> [in]位掩码的标志控制提供程序添加的。 可以设置以下标志：
    
  - MAPI_DIALOG： 显示一个对话框，提示配置信息。
      
  - MAPI_UNICODE： 提供程序名称和字符串属性采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。
    
 _lpUID_
  
> [输出]一个指向[MAPIUID](mapiuid.md)结构，其中包含代表要添加的提供程序的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 提供程序已成功添加到邮件服务。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>说明

**IProviderAdmin::CreateProvider**方法向邮件服务的服务提供商。 _LpszProvider_参数必须指向属于邮件服务提供程序的名称。 **CreateProvider**不验证该名称是否与服务; 中提供的名称匹配如果传递的名称不匹配的服务名称，调用成功，但结果将无法预料。 大多数消息服务不允许提供程序添加或删除配置文件时使用。 
  
毕竟可用信息有关服务提供程序已添加到配置文件从 Mapisvc.inf 文件， **CreateProvider** _ulContext_参数设置为 MSG_SERVICE_ 呼叫消息服务的入口点函数PROVIDER_CREATE。 如果 MAPI_DIALOG 设置**CreateProvider**方法的_ulFlags_参数中，在_ulUIParam_和_ulFlags_参数中的值还传递到入口点函数。 这些其他参数启用要显示其属性表，以便用户可以输入配置设置的服务提供程序。 
  
## <a name="see-also"></a>另请参阅

- [MAPIUID](mapiuid.md)  
- [MSGSERVICEENTRY](msgserviceentry.md)  
- [SPropValue](spropvalue.md)  
- [IProviderAdmin : IUnknown](iprovideradminiunknown.md)

