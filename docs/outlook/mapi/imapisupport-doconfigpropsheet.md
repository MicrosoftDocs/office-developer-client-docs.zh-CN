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
  
> [in]父窗口的句柄属性表。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpszTitle_
  
> [in]指向项目标题的属性表。
    
 _lpDisplayTable_
  
> [in]指向显示表的指针，该显示表描述要显示在属性表。
    
 _lpConfigData_
  
> [in]指向 [IMAPIProp](imapipropiunknown.md) 实现（用于访问要显示在 属性表 上的配置属性）的指针。 
    
 _ulTopPage_
  
> [in]从零开始到默认页面的索引属性表。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 配置属性表显示。
    
## <a name="remarks"></a>备注

**IMAPISupport：:D oConfigPropsheet** 方法针对所有支持对象实现。 **DoConfigPropSheet** 提供了用于显示服务提供程序和邮件服务的属性的标准用户界面。 应针对所有配置属性显示使用此标准对话框，以便用户受益于一致的Windows界面。 
  
服务提供商在 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md)方法的实现过程中，或者从用于显示属性详细信息的按钮调用 **DoConfigPropSheet。** 邮件服务从 **邮件服务入口点函数调用 DoConfigPropSheet。** 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过调用 [BuildDisplayTable](builddisplaytable.md)函数或自定义代码创建 _lpDisplayTable_ 参数指向的显示表。 
  
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

