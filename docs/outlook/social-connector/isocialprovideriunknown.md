---
title: ISocialProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c9f4dd4-65f6-446f-8b86-a375ce402658
description: 表示 Outlook Social Connector (.osc) 提供程序的实例。
ms.openlocfilehash: f28b8343d92b09455b6049f421b839efbda21c1a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285482"
---
# <a name="isocialprovider--iunknown"></a>ISocialProvider : IUnknown

表示 Outlook Social Connector (.osc) 提供程序的实例。
  
## <a name="members"></a>Members

下表显示了**ISocialProvider**接口上可用的成员。 
  
|**Name**|**成员类型**|**Description**|
|:-----|:-----|:-----|
|[DefaultSiteUrls](isocialprovider-defaultsiteurls.md) <br/> |属性  <br/> |返回一个字符串数组, 这些字符串指定 .osc 提供程序的网站 url。  <br/> |
|[GetAutoConfiguredSession](isocialprovider-getautoconfiguredsession.md) <br/> |方法  <br/> |获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。  <br/> |
|[GetCapabilities](isocialprovider-getcapabilities.md) <br/> |方法  <br/> |获取描述提供程序功能的字符串。  <br/> |
|[GetSession](isocialprovider-getsession.md) <br/> |方法  <br/> |获取[ISocialSession](isocialsessioniunknown.md)接口。  <br/> |
|[GetStatusSettings](isocialprovider-getstatussettings.md) <br/> |方法  <br/> |目前不支持此方法。  <br/> |
|[Load](isocialprovider-load.md) <br/> |方法  <br/> |初始化 .osc 提供程序。  <br/> |
|[SocialNetworkGuid](isocialprovider-socialnetworkguid.md) <br/> |属性  <br/> |返回表示社交网络的唯一标识符的 GUID。  <br/> |
|[SocialNetworkIcon](isocialprovider-socialnetworkicon.md) <br/> |属性  <br/> |返回表示社交网络图标的字节数组。  <br/> |
|[SocialNetworkName](isocialprovider-socialnetworkname.md) <br/> |属性  <br/> |返回一个字符串, 表示社交网络名称。  <br/> |
|[Version](isocialprovider-version.md) <br/> |属性  <br/> |返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。  <br/> |
   
## <a name="remarks"></a>注解

一个 .osc 提供程序必须实现此接口才能与 .osc 进行通信。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

