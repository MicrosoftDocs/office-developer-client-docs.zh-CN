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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 06341f897a7865c09a565db67bb409fc9f49f8da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775613"
---
# <a name="imapisupportdoconfigpropsheet"></a>IMAPISupport::DoConfigPropsheet

  
  
**适用于**： Outlook 
  
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
  
> [in]属性表的父窗口句柄。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpszTitle_
  
> [in]一个指向属性表的标题。
    
 _lpDisplayTable_
  
> [in]指向显示表在属性表中描述的控件显示的指针。
    
 _lpConfigData_
  
> [in]指向要用于访问的配置属性用于在属性表中显示的[IMAPIProp](imapipropiunknown.md)实现的指针。 
    
 _ulTopPage_
  
> [in]属性表的默认顶级网页到一个从零开始的索引。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 显示已配置的属性表。
    
## <a name="remarks"></a>说明

对于所有支持对象实现**IMAPISupport::DoConfigPropsheet**方法。 **DoConfigPropSheet**提供标准用户界面，用于显示服务提供商和消息服务的属性。 使用户受益于一致的 Windows 接口，应用于所有配置属性显示此标准的对话框。 
  
服务提供商调用**DoConfigPropSheet**作为其实现[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)方法时，或者从用来显示属性的详细信息的按钮的一部分。 消息服务从其消息服务入口点函数调用**DoConfigPropSheet** 。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以创建通过调用[BuildDisplayTable](builddisplaytable.md)函数或自定义代码_lpDisplayTable_参数指向显示表。 
  
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

