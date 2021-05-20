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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439728"
---
# <a name="imapistatussettingsdialog"></a>IMAPIStatus::SettingsDialog

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Displays a 属性表 that enables the user to change a service provider's configuration This method is not supported in status objects that MAPI implements.
  
```cpp
HRESULT SettingsDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]配置窗口的父窗口的属性表。
    
 _ulFlags_
  
> [in]控制屏幕显示的标志的位掩码属性表。 可以设置以下标志：
    
UI_READONLY 
  
> 建议提供程序不应允许用户更改配置属性。 此标志只是一个建议;可忽略。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 配置属性表已成功显示。
    
MAPI_E_NO_SUPPORT 
  
> status 对象不支持此方法，如 PR_RESOURCE_METHODS ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md) 属性中缺少 STATUS_SETTINGS_DIALOG 标志) 。
    
## <a name="remarks"></a>备注

**IMAPIStatus：：SettingsDialog** 方法显示配置属性表。 所有服务提供程序都应支持 **SettingsDialog** 方法，但不是必需的。 服务提供商可以实施自己的属性表或使用支持对象的 [IMAPISupport：:D oConfigPropsheet 方法](imapisupport-doconfigpropsheet.md) 中提供的实现。 **DoConfigPropsheet** 生成读/写属性表。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果远程传输提供程序有任何设置，则它应执行以下操作：
  
- 打开传输提供程序的配置文件部分。
    
- 从配置文件获取传输提供程序的属性设置。
    
- 在对话框中显示属性设置。
    
- 如果对话框允许编辑属性设置，请检查新设置是否有效，然后将它们存储回传输提供程序的配置文件部分。
    
- 返回S_OK或上述步骤中返回的任何错误值。
    
## <a name="notes-to-callers"></a>给调用方的说明

可以使用通过 **SettingsDialog** 属性表显示的列表来执行各种任务，例如： 
  
- 指定默认邮件存储。
    
- 指定传输顺序。
    
- 指定用于浏览的默认通讯簿容器。
    
- 指定用于解析不明确名称的搜索顺序。
    
- 指定默认个人通讯簿。
    
服务提供程序可以实施读/写、只读或权限混合的属性表，具体取决于属性。 服务提供商可以通过设置属性限制对单个属性实现不同的权限。 属性表的默认模式为读/写。 可以通过在调用 **SettingsDialog** 中设置 UI_READONLY 标志来请求只读属性表。 能够实现只读属性表的服务提供商可以这样做。 但是，由于某些服务提供商无法替代默认模式，因此您必须准备好处理任一类型的属性表。 
  
由于此操作始终涉及用户界面，因此只有交互式客户端应调用 **SettingsDialog**。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)
  
[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

