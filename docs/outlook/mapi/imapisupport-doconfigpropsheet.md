---
title: IMAPISupportDoConfigPropsheet
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoConfigPropsheet
api_type:
- COM
ms.assetid: 3899c49c-a0ec-4dca-92e8-e801cd4908cf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cd8727104af694d456074614b5ea7c222c9b91b9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429011"
---
# <a name="imapisupportdoconfigpropsheet"></a>IMAPISupport::DoConfigPropsheet

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示配置属性表。
  
```cpp
HRESULT DoConfigPropsheet(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPSTR lpszTitle,
  LPMAPITABLE lpDisplayTable,
  LPMAPIPROP lpConfigData,
  ULONG ulTopPage
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时属性表的父窗口的句柄。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lpszTitle_
  
> 实时指向属性表的标题的指针。
    
 _lpDisplayTable_
  
> 实时指向说明要在属性表上显示的控件的显示表的指针。
    
 _lpConfigData_
  
> 实时指向[IMAPIProp](imapipropiunknown.md)实现的指针, 该实现将用于访问要显示在属性表上的配置属性。 
    
 _ulTopPage_
  
> 实时属性表的默认顶部页面的从零开始的索引。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 显示配置属性表。
    
## <a name="remarks"></a>说明

**IMAPISupport::D oconfigpropsheet**方法是为所有支持对象实现的。 **DoConfigPropSheet**提供了用于显示服务提供程序和邮件服务的属性的标准用户界面。 应将此标准对话框用于显示所有配置属性, 以便用户可以从一致的 Windows 界面中受益。 
  
服务提供程序将**DoConfigPropSheet**作为[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)方法的实现的一部分或从用于显示属性的详细信息的按钮进行调用。 邮件服务从其邮件服务入口点函数调用**DoConfigPropSheet** 。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过调用[BuildDisplayTable](builddisplaytable.md)函数或使用自定义代码来创建由_lpDisplayTable_参数指向的显示表。 
  
## <a name="see-also"></a>另请参阅



[BuildDisplayTable](builddisplaytable.md)
  
[CreateIProp](createiprop.md)
  
[IABProvider::Logon](iabprovider-logon.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)
  
[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

