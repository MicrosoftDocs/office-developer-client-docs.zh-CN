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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 72dddca5a8079374600e05b96a24cbbc25e7f7f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279554"
---
# <a name="iprovideradmincreateprovider"></a>IProviderAdmin::CreateProvider

**适用于**：Outlook 2013 | Outlook 2016 
  
向邮件服务中添加服务提供程序。 
  
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
  
> 实时指向要添加的提供程序的名称的指针。
    
 _cValues_
  
> 实时由_lpProps_参数指向的属性值的计数。 
    
 _lpProps_
  
> 实时指向描述要添加的提供程序的属性的属性值数组的指针。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。 如果在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 则使用_ulUIParam_参数。 
    
 _ulFlags_
  
> 实时用于控制提供程序添加的标志的位掩码。 可以设置以下标志:
    
  - MAPI_DIALOG: 显示一个对话框, 提示输入配置信息。
      
  - MAPI_UNICODE: 提供程序名称和字符串属性采用 UNICODE 格式。 如果未设置 MAPI_UNICODE 标志, 则这些字符串将采用 ANSI 格式。
    
 _lpUID_
  
> 排除指向[MAPIUID](mapiuid.md)结构的指针, 该对象包含表示要添加的提供程序的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功将该提供程序添加到邮件服务中。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

**IProviderAdmin:: CreateProvider**方法将服务提供程序添加到邮件服务中。 _lpszProvider_参数必须指向属于邮件服务的提供程序的名称。 **CreateProvider**不验证该名称是否与服务中的提供程序的名称匹配;如果传递的名称与服务名称不匹配, 则调用会成功, 但结果是不可预知的。 大多数邮件服务在使用配置文件时不允许添加或删除提供程序。 
  
从 mapisvc.inf 文件中将有关服务提供程序的所有可用信息添加到配置文件后, **CreateProvider**将调用邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_PROVIDER_CREATE。 如果在**CreateProvider**方法的_ulFlags_参数中设置了 MAPI_DIALOG, 则_ulUIParam_和_ulFlags_参数中的值也会传递到入口点函数。 这些附加参数使服务提供程序能够显示其属性表, 以便用户可以输入配置设置。 
  
## <a name="see-also"></a>另请参阅

- [MAPIUID](mapiuid.md)  
- [MSGSERVICEENTRY](msgserviceentry.md)  
- [SPropValue](spropvalue.md)  
- [IProviderAdmin : IUnknown](iprovideradminiunknown.md)

