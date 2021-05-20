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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430803"
---
# <a name="iprovideradmincreateprovider"></a>IProviderAdmin::CreateProvider

**适用于**：Outlook 2013 | Outlook 2016 
  
将服务提供程序添加到邮件服务。 
  
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
  
> [in]指向要添加的提供程序的名称的指针。
    
 _cValues_
  
> [in]  _lpProps_ 参数指向的属性值计数。 
    
 _lpProps_
  
> [in]指向描述要添加的提供程序的属性的属性值数组的指针。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 如果在  _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，则使用  _ulUIParam_ 参数。 
    
 _ulFlags_
  
> [in]控制提供程序添加的标志的位掩码。 可以设置以下标志：
    
  - MAPI_DIALOG：显示一个对话框，提示输入配置信息。
      
  - MAPI_UNICODE：提供程序名称和字符串属性采用 Unicode 格式。 如果未MAPI_UNICODE，则这些字符串采用 ANSI 格式。
    
 _lpUID_
  
> [out]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含表示要添加的提供程序的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 提供程序已成功添加到邮件服务。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

**IProviderAdmin：：CreateProvider** 方法向邮件服务添加服务提供程序。 _lpszProvider_ 参数必须指向属于邮件服务的提供程序的名称。 **CreateProvider** 不验证名称是否与服务中的提供程序的名称匹配;如果传递的名称与服务名称不匹配，则调用成功，但结果不可预测。 大多数邮件服务不允许在配置文件使用时添加或删除提供程序。 
  
将有关服务提供商的所有可用信息从 Mapisvc.inf 文件添加到配置文件后 **，CreateProvider** 将调用邮件服务的入口点函数  _，ulContext_ 参数设置为 MSG_SERVICE_PROVIDER_CREATE。 如果MAPI_DIALOG **CreateProvider** 方法的  _ulFlags_ 参数中设置了该参数，  _则 ulUIParam_ 和  _ulFlags_ 参数中的值也将传递给入口点函数。 这些附加参数使服务提供商能够显示其属性表，以便用户可以输入配置设置。 
  
## <a name="see-also"></a>另请参阅

- [MAPIUID](mapiuid.md)  
- [MSGSERVICEENTRY](msgserviceentry.md)  
- [SPropValue](spropvalue.md)  
- [IProviderAdmin : IUnknown](iprovideradminiunknown.md)

