---
title: ISocialProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1c9f4dd4-65f6-446f-8b86-a375ce402658
description: 表示 OSC 提供程序中的 Outlook Social Connector () 实例。
ms.openlocfilehash: f28b8343d92b09455b6049f421b839efbda21c1a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409956"
---
# <a name="isocialprovider--iunknown"></a>ISocialProvider : IUnknown

表示 OSC 提供程序中的 Outlook Social Connector () 实例。
  
## <a name="members"></a>Members

下表显示了 **ISocialProvider** 接口上可用的成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[DefaultSiteUrls](isocialprovider-defaultsiteurls.md) <br/> |属性  <br/> |返回一个字符串数组，该数组指定 OSC 提供程序的网站 URL。  <br/> |
|[GetAutoConfiguredSession](isocialprovider-getautoconfiguredsession.md) <br/> |方法  <br/> |获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。  <br/> |
|[GetCapabilities](isocialprovider-getcapabilities.md) <br/> |方法  <br/> |获取一个描述提供程序功能的字符串。  <br/> |
|[GetSession](isocialprovider-getsession.md) <br/> |方法  <br/> |获取 [ISocialSession](isocialsessioniunknown.md) 接口。  <br/> |
|[GetStatusSettings](isocialprovider-getstatussettings.md) <br/> |方法  <br/> |此方法当前不受支持。  <br/> |
|[Load](isocialprovider-load.md) <br/> |方法  <br/> |初始化 OSC 提供程序。  <br/> |
|[SocialNetworkGuid](isocialprovider-socialnetworkguid.md) <br/> |属性  <br/> |返回表示社交网络的唯一标识符的 GUID。  <br/> |
|[SocialNetworkIcon](isocialprovider-socialnetworkicon.md) <br/> |属性  <br/> |返回一个字节数组，该数组代表社交网络的图标。  <br/> |
|[SocialNetworkName](isocialprovider-socialnetworkname.md) <br/> |属性  <br/> |返回一个代表社交网络名称的字符串。  <br/> |
|[版本](isocialprovider-version.md) <br/> |属性  <br/> |返回一个字符串，该字符串表示此社交网络的提供程序的版本号。  <br/> |
   
## <a name="remarks"></a>备注

OSC 提供程序必须实现此接口以与 OSC 通信。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

