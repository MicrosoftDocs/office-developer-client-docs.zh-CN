---
title: WIZARDENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.WIZARDENTRY
api_type:
- COM
ms.assetid: e807c6b5-06cd-4ade-9d9e-69ba6abd1614
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 907984a80dbb6c5464f95def1481d002f9d6638a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329552"
---
# <a name="wizardentry"></a>WIZARDENTRY

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个服务提供程序入口点函数, 配置文件向导调用它以检索足够的信息, 以显示提供程序的配置属性表。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiwz  <br/> |
|定义的函数实现者:  <br/> |服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI 配置文件向导  <br/> |
   
```cpp
ULONG WIZARDENTRY(
  HINSTANCE hProviderDLLInstance,
  LPSTR FAR * lpcsResourceName,
  DLGPROC FAR * lppDlgProc,
  LPMAPIPROP lpMAPIProp,
  LPMAPISUPPORTOBJECT lpMapiSupportObject
);
```

## <a name="parameters"></a>参数

 _hProviderDLLInstance_
  
> 实时服务提供程序的 DLL 的实例句柄。 
    
 _lpcsResourceName_
  
> 排除指向一个字符串的指针, 该字符串包含在配置过程中应由配置文件向导显示的对话框资源的完整名称。 字符串的最大大小 (包括 NULL 终止符) 为32个字符。 
    
 _lppDlgProc_
  
> 排除指向标准 Windows 对话框过程的指针, 该过程将由配置文件向导调用以通知提供程序的各种事件。 
    
 _lpMAPIProp_
  
> 实时指向提供对配置属性的访问权限的属性接口实现的指针。 
    
 _lpMapiSupportObject_
  
> 实时指向适用于此会话的 MAPI 支持对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功调用服务提供程序的**WIZARDENTRY**函数。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止操作完成。
    
## <a name="remarks"></a>注解

"配置文件向导" 在准备好显示服务提供商的配置用户界面时调用基于**WIZARDENTRY**的函数。 配置文件向导完成配置所有提供程序后, 通过调用[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)将配置属性写入配置文件。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

基于**WIZARDENTRY**的函数的名称必须放在 mapisvc.inf 中的 WIZARD_ENTRY_NAME 条目中。 
  
资源名称是将在 "配置文件向导" 窗格中呈现的对话框资源的名称。 传递回的资源需要包含单个对话框资源中的所有页面。 当配置文件向导收到此资源时, 它将忽略对话框样式 (而不是控件样式), 并将所有控件创建为 "配置文件向导" 页的子级。 所有控件最初都处于隐藏状态。 提供程序应确保其控件的坐标为零或从零开始, 并且不超过最大宽度为200的对话框单元, 最大高度为150个对话框单位。 低于400的控制标识符是为配置文件向导保留的。 "配置文件向导" 在提供程序的用户界面上方的加粗文本中显示提供程序的标题。 
  
_lpMAPIProp_参数中提供的属性接口指针应由提供程序保留, 以供将来参考。 配置文件向导仅处理最基本的一组属性, 并且提供程序可以使用属性接口实现来包含其他属性。 在配置过程中, 提供程序应将其配置属性添加到实现属性接口的对象。 配置完所有提供程序后, 配置文件向导会将这些属性添加到配置文件中。 
  
有关如何使用此函数的详细信息, 请参阅[支持邮件服务配置](supporting-message-service-configuration.md)。 
  

