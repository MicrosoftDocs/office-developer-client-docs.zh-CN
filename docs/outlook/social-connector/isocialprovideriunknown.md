---
title: ISocialProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c9f4dd4-65f6-446f-8b86-a375ce402658
description: 代表 Outlook Social Connector (OSC) 提供程序的实例。
ms.openlocfilehash: 912b2d92137febe80e0d97362e0a490f138b2e66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779348"
---
# <a name="isocialprovider--iunknown"></a>ISocialProvider : IUnknown

代表 Outlook Social Connector (OSC) 提供程序的实例。
  
## <a name="members"></a>Members

下表显示了**ISocialProvider**接口上可用的成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[DefaultSiteUrls](isocialprovider-defaultsiteurls.md) <br/> |属性  <br/> |返回一个指定 OSC 提供程序网站 Url 的字符串数组。  <br/> |
|[GetAutoConfiguredSession](isocialprovider-getautoconfiguredsession.md) <br/> |方法  <br/> |获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。  <br/> |
|[GetCapabilities](isocialprovider-getcapabilities.md) <br/> |方法  <br/> |获取一个字符串，描述提供程序功能。  <br/> |
|[GetSession](isocialprovider-getsession.md) <br/> |方法  <br/> |获取[ISocialSession](isocialsessioniunknown.md)接口。  <br/> |
|[GetStatusSettings](isocialprovider-getstatussettings.md) <br/> |方法  <br/> |当前不支持此方法。  <br/> |
|[加载](isocialprovider-load.md) <br/> |方法  <br/> |初始化 OSC 提供程序。  <br/> |
|[SocialNetworkGuid](isocialprovider-socialnetworkguid.md) <br/> |属性  <br/> |返回一个 GUID 值，该值代表社交网络的唯一标识符。  <br/> |
|[SocialNetworkIcon](isocialprovider-socialnetworkicon.md) <br/> |属性  <br/> |返回表示图标的社交网络的字节数组。  <br/> |
|[SocialNetworkName](isocialprovider-socialnetworkname.md) <br/> |属性  <br/> |返回 string 类型的值，该值代表社交网络名称。  <br/> |
|[版本](isocialprovider-version.md) <br/> |属性  <br/> |返回一个字符串，表示为此社交网络提供程序的版本号。  <br/> |
   
## <a name="remarks"></a>说明

OSC 提供程序必须实现此接口与 OSC 进行通信。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

