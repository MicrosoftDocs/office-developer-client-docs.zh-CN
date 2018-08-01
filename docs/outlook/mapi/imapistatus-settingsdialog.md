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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 09a14a3cc9f77527c6bc254dc703328f2c9ce9f5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775587"
---
# <a name="imapistatussettingsdialog"></a>IMAPIStatus::SettingsDialog

  
  
**适用于**： Outlook 
  
显示使用户能够更改服务提供商的配置中 MAPI 实现的状态对象不支持此方法的属性表。
  
```cpp
HRESULT SettingsDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]配置属性表的父窗口句柄。
    
 _ulFlags_
  
> [in]位掩码的标志的控件显示的属性表。 可以设置以下标记：
    
UI_READONLY 
  
> 建议的提供程序不应使用户能够更改配置属性。 此标志为只建议;可以忽略它。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 配置属性表显示成功。
    
MAPI_E_NO_SUPPORT 
  
> 状态对象不支持此方法，由 STATUS_SETTINGS_DIALOG 标志**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中不存在。
    
## <a name="remarks"></a>说明

**IMAPIStatus::SettingsDialog**方法显示配置属性表。 所有服务提供商应都支持**留待**方法，但不是必需的。 服务提供商可以实现自己的属性表或使用支持对象的[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法中提供的实现。 **DoConfigPropsheet**生成读/写属性表。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果远程传输提供程序的任何设置，它应执行以下操作：
  
- 打开传输提供程序的配置文件部分。
    
- 获取从配置文件的传输提供程序的属性设置。
    
- 在对话框中显示的属性设置。
    
- 如果在对话框中，编辑属性设置的检查新的设置有效，并将它们存储返回在传输提供程序的配置文件部分。
    
- 返回 S_OK 或在前面步骤中返回的任何错误值。
    
## <a name="notes-to-callers"></a>给调用方的说明

属性表通过**留待**显示可用于执行各种任务，如下所示： 
  
- 指定默认邮件存储区。
    
- 指定传输顺序。
    
- 指定用于浏览默认通讯簿容器。
    
- 指定搜索顺序解决不明确的名称。
    
- 指定默认个人通讯簿。
    
为读/写，只读的的属性表或混合的权限，具体取决于该属性，可以实现服务提供商。 服务提供商可以通过设置属性限制单个属性实现不同的权限。 属性表的默认模式是可读写。 您可以通过在您调用**留待**中设置 UI_READONLY 标志请求只读属性表。 能够实现只读属性页的服务提供商可以这样做。 但是，因为某些服务提供程序无法重写默认模式，您必须是准备处理任一类型的属性表。 
  
由于始终在此操作中涉及的用户界面，则仅交互式客户端应调用**留待**。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)
  
[PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
  
[IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

