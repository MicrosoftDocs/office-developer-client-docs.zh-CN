---
title: LAUNCHWIZARDENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LAUNCHWIZARDENTRY
api_type:
- COM
ms.assetid: 5778dffa-f01b-46b3-9c19-862793740918
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c1509918eb587c17deebf95317cf57b4ab19928a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270187"
---
# <a name="launchwizardentry"></a>LAUNCHWIZARDENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义用于启动配置文件向导应用程序的函数, 以将一个或多个邮件服务添加到配置文件。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiwz  <br/> |
|定义的函数实现者:  <br/> |MAPI  <br/> |
|定义的函数调用者:  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT LAUNCHWIZARDENTRY(
  HWND hParentWnd,
  ULONG ulFlags,
  LPCSTR FAR * lppszServiceNameToAdd,
  ULONG cbBufferMax,
  LPSTR lpszNewProfileName
);
```

## <a name="parameters"></a>参数

 _hParentWnd_
  
> 实时呼叫者父窗口的句柄。 如果调用方没有父窗口, 则_hParentWnd_参数应为 NULL。 
    
 _ulFlags_
  
> 实时指示配置文件向导选项的标志的位掩码。 可以设置以下标志:
    
MAPI_PW_ADD_SERVICE_ONLY 
  
> 配置文件向导是仅添加通过_lppszServiceNameToAdd_参数列出的邮件服务, 而不是显示其用于选择邮件服务的页面。 
    
MAPI_PW_FIRST_PROFILE 
  
> 要创建的配置文件是此工作站的第一个配置文件。 
    
MAPI_PW_HIDE_SERVICES_LIST 
  
> 不应显示用于选择 "邮件服务" 的配置文件向导的页面。 
    
MAPI_PW_LAUNCHED_BY_CONFIG 
  
> "配置文件向导" 由 "控制面板" 配置应用程序启动。 
    
MAPI_PW_PROVIDER_UI_ONLY 
  
> 仅应显示服务提供商的配置对话框, 并且不应显示配置文件向导的页面。 仅当设置了 MAPI_PW_ADD_SERVICE_ONLY 标志时, 才能设置此标志。 
    
 _lppszServiceNameToAdd_
  
> 实时指向包含要添加到配置文件中的邮件服务的名称的字符串数组的指针。 数组必须以 NULL 值终止。 
    
 _cbBufferMax_
  
> 实时由_lpszNewProfileName_参数指向的缓冲区的大小。 
    
 _lpszNewProfileName_
  
> 排除指向基于**LAUNCHWIZARDENTRY**的函数的字符串缓冲区的指针返回所创建的配置文件的名称。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止操作完成。 可能的原因包括初始化配置文件向导的 MAPI 子系统失败、无法访问默认配置文件以及从对话框返回错误。
    
## <a name="remarks"></a>注解

**LAUNCHWIZARDENTRY**函数原型的 MAPI 实现是 mapi 配置文件向导应用程序的入口点。 MAPI 将此入口点命名为**LaunchWizard**。 
  
在_ulFlags_参数中设置 MAPI_PW_ADD_SERVICE_ONLY 标志时, 将应用以下规则: 
  
- MAPI_PW_LAUNCHED_BY_CONFIG 标志禁止显示欢迎页面。 
    
- 仅当没有默认配置文件时, MAPI_PW_HIDE_SERVICES_LIST 和 MAPI_PW_PROVIDER_UI_ONLY 标志才有用。 在这种情况下, 这些标志决定要显示哪个配置文件向导页。 
    
- 如果存在默认配置文件, 则不会显示任何配置文件向导页。 
    
- 如果存在默认配置文件, 则仅通过_lppszServiceNameToAdd_参数列出了一个邮件服务, 并且该邮件服务已在默认配置文件中, 配置文件向导返回 S_OK, 而不向配置文件添加任何内容。 
    
对于要添加到配置文件中的每个邮件服务, 配置文件向导将根据[MSGSERVICEENTRY](msgserviceentry.md)原型调用服务的入口点函数。 对于从要添加到配置文件中的邮件服务中选择的每个服务提供程序, "配置文件向导" 将根据[WIZARDENTRY](wizardentry.md)原型调用提供程序的入口点函数。 在交互式配置过程中, 属性页中的每个用户事件都会使配置文件向导根据[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型调用提供程序的回调函数。 
  
如果要添加到配置文件中的服务提供程序支持配置文件向导页, 则它必须允许配置文件的编程配置。
  

