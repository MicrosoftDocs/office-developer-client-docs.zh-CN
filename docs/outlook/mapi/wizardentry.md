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
ms.openlocfilehash: 2c307d18c5b62e5190aa10632a47a3f16b80e81f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779095"
---
# <a name="wizardentry"></a>WIZARDENTRY

  
  
**适用于**： Outlook 
  
定义种服务提供程序入口点函数，其配置文件向导调用来检索足够的信息来显示提供程序的配置属性表。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiwz.h  <br/> |
|通过实施定义的函数：  <br/> |服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI 配置文件向导  <br/> |
   
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
  
> [in]服务提供商的 DLL 实例句柄。 
    
 _lpcsResourceName_
  
> [输出]指针指向包含配置过程中配置文件向导应显示对话框资源的完整名称的字符串。 字符串，包括 NULL 终止符，最大大小为 32 个字符。 
    
 _lppDlgProc_
  
> [输出]指向标准 Windows 对话框过程将由配置文件向导来通知的提供程序的各种事件调用的指针。 
    
 _lpMAPIProp_
  
> [in]提供对的配置属性访问属性接口实现的指针。 
    
 _lpMapiSupportObject_
  
> [in]指向适用于此会话的 MAPI 支持对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功调用了服务提供商的**WIZARDENTRY**函数。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知的原点出现错误，无法完成操作。
    
## <a name="remarks"></a>说明

配置文件向导调用**WIZARDENTRY**基于函数，以显示服务提供商的配置用户界面的准备就绪时。 完成配置所有提供程序配置文件向导后，它将通过调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)到配置文件写入的配置属性。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

必须在 MAPISVC.INF WIZARD_ENTRY_NAME 条目中放置**WIZARDENTRY**基于函数的名称。 
  
资源名称是对话框资源的将呈现窗格中的配置文件向导。 传递后需要包含单个对话框资源中的所有页面的资源。 当配置文件向导收到此资源时，它将忽略该对话框样式，但不是的控件样式，并作为子级的配置文件向导页上创建的所有控件。 所有控件最初处于隐藏都状态。 提供程序应进行确保其控件的坐标都零或从零开始，，它们不超过 200 个对话框单位的最大宽度和 150 个对话框单位的最大高度。 下面的 400 控件标识符被保留，供配置文件向导。 配置文件向导加粗文本上方提供程序的用户界面中显示的提供程序的标题。 
  
_LpMAPIProp_参数中提供的属性接口指针应保留以供将来参考服务提供商。 配置文件向导处理仅最基本的一组属性，并提供程序可以使用该属性接口实现包括其他属性。 在配置期间，提供程序应将其配置属性添加到实现属性接口的对象。 已配置的所有提供商之后，配置文件向导会将这些属性添加到配置文件。 
  
有关如何使用此函数的详细信息，请参阅[支持的消息服务配置](supporting-message-service-configuration.md)。 
  

