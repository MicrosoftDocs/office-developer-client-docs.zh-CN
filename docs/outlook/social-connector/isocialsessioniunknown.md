---
title: ISocialSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0fe423d7-b044-479b-89ad-c39620eedd65
description: 代表与社交网络站点的连接。
ms.openlocfilehash: ee3a8aa72ea187b4c211bc7a49e8a2dbe170adad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779250"
---
# <a name="isocialsession--iunknown"></a>ISocialSession : IUnknown

代表与社交网络站点的连接。
  
## <a name="members"></a>Members

下表显示了**ISocialSession**接口上可用的成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[FindPerson](isocialsession-findperson.md) <br/> |方法  <br/> |获取一个值，该值代表一个或多个人员_userID_参数匹配的字符串。  <br/> |
|[FollowPerson](isocialsession-followperson.md) <br/> |方法  <br/> |添加为朋友社交网络登录用户的_电子邮件地址_参数标识的人员。  <br/> |
|[GetActivities](isocialsession-getactivities.md) <br/> |方法  <br/> |此方法已被弃用在 Outlook Social Connector (OSC) 1.1。  <br/> |
|[GetLoggedOnUser](isocialsession-getloggedonuser.md) <br/> |方法  <br/> |获取一个值，该值代表登录用户的[ISocialProfile](isocialprofileisocialperson.md)接口。  <br/> |
|[GetLogonUrl](isocialsession-getlogonurl.md) <br/> |方法  <br/> |获取一个字符串，表示用于 web 身份验证过程中显示给用户的基于浏览器的表单的 URL。  <br/> |
|[GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) <br/> |方法  <br/> |获取一个字符串，表示对于给定的社交网络连接的唯一的社交网络标识符。  <br/> |
|[GetPerson](isocialsession-getperson.md) <br/> |方法  <br/> |获取基于_用户 Id_参数[ISocialPerson](isocialpersoniunknown.md)接口。  <br/> |
|[LoggedOnUserID](isocialsession-loggedonuserid.md) <br/> |属性  <br/> |返回一个字符串，表示当前已登录的用户的社交网络用户 ID。  <br/> |
|[LoggedOnUserName](isocialsession-loggedonusername.md) <br/> |属性  <br/> |返回一个字符串，表示在登录时使用的用户名。  <br/> |
|[登录](isocialsession-logon.md) <br/> |方法  <br/> |登录到社交网络站点使用指定的用户名和密码。  <br/> |
|[LogonWeb](isocialsession-logonweb.md) <br/> |方法  <br/> |登录到使用基于表单的身份验证的社交网络站点。  <br/> |
|[SiteUrl](isocialsession-siteurl.md) <br/> |属性  <br/> |设置的社交网络站点的 URL。  <br/> |
|[UnFollowPerson](isocialsession-unfollowperson.md) <br/> |方法  <br/> |删除为社交网络上朋友_userID_参数标识的人员。  <br/> |
   
## <a name="remarks"></a>说明

OSC 提供程序必须实现此接口与 OSC 进行通信。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

