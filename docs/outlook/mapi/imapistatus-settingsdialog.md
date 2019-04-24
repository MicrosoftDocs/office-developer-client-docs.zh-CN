---
title: IMAPIStatusSettingsDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.SettingsDialog
api_type:
- COM
ms.assetid: e931246e-7fff-4116-a9fc-f685988e21e8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1e9d390a895490f2f7445c5f1ed6e0bde3a87639
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331540"
---
# <a name="imapistatussettingsdialog"></a>IMAPIStatus::SettingsDialog

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示允许用户更改服务提供程序配置的属性表。 MAPI 实现的 status 对象中不支持此方法。
  
```cpp
HRESULT SettingsDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时配置属性表的父窗口的句柄。
    
 _ulFlags_
  
> 实时用于控制属性表的显示的标志的位掩码。 可以设置以下标志:
    
UI_READONLY 
  
> 建议提供程序不应使用户能够更改配置属性。 此标志只是一个建议;可以忽略它。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功显示配置属性表。
    
MAPI_E_NO_SUPPORT 
  
> status 对象不支持此方法, 正如**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中缺少 STATUS_SETTINGS_DIALOG 标志所指示的那样。
    
## <a name="remarks"></a>注解

**IMAPIStatus:: SettingsDialog**方法显示一个配置属性表。 所有服务提供程序都应支持**SettingsDialog**方法, 但这并不是必需的。 服务提供程序可以实现自己的属性表, 也可以使用支持对象的 IMAPISupport 中提供的实现[::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法。 **DoConfigPropsheet**生成读/写属性表。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果远程传输提供程序具有任何设置, 则应执行以下操作:
  
- 打开传输提供程序的 "配置文件" 部分。
    
- 从配置文件中获取传输提供程序的属性设置。
    
- 在对话框中显示属性设置。
    
- 如果对话框允许编辑属性设置, 请检查新设置是否有效, 并将其重新存储在传输提供程序的配置文件部分中。
    
- 返回 S_OK 或在前面的步骤中返回的任何错误值。
    
## <a name="notes-to-callers"></a>给调用方的说明

您可以使用通过**SettingsDialog**显示的属性表执行各种任务, 如以下操作: 
  
- 指定默认邮件存储。
    
- 指定传输顺序。
    
- 指定用于浏览的默认通讯簿容器。
    
- 指定用于解析不明确名称的搜索顺序。
    
- 指定默认的个人通讯簿。
    
服务提供程序可以实现可读写、只读或混合权限的属性表, 具体取决于属性。 服务提供程序可以通过设置属性限制对各个属性实现不同的权限。 属性表的默认模式为 "读/写"。 您可以通过在对**SettingsDialog**的调用中设置 UI_READONLY 标志来请求只读属性表。 能够实现只读属性表的服务提供程序可以执行此操作。 但是, 由于某些服务提供程序无法覆盖默认模式, 因此必须准备好处理任一类型的属性表。 
  
由于用户界面始终包含在此操作中, 因此只有交互客户端才应调用**SettingsDialog**。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)
  
[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

