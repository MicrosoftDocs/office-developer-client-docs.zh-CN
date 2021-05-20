---
title: ISocialSession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0fe423d7-b044-479b-89ad-c39620eedd65
description: 表示与社交网络网站的连接。
ms.openlocfilehash: c60fab1c27d2f761db28ed06bb45080857630e8d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437824"
---
# <a name="isocialsession--iunknown"></a>ISocialSession : IUnknown

表示与社交网络网站的连接。
  
## <a name="members"></a>Members

下表显示了 **ISocialSession** 接口上可用的成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[FindPerson](isocialsession-findperson.md) <br/> |方法  <br/> |获取一个字符串，代表与 userID 参数匹配的  _一个或多个_ 人员。  <br/> |
|[FollowPerson](isocialsession-followperson.md) <br/> |方法  <br/> |将  _emailAddress_ 参数标识的人添加为社交网络上已登录用户的好友。  <br/> |
|[GetActivities](isocialsession-getactivities.md) <br/> |方法  <br/> |在 OSC 1.1 Outlook Social Connector (中) 此方法。  <br/> |
|[GetLoggedOnUser](isocialsession-getloggedonuser.md) <br/> |方法  <br/> |获取一个代表已登录用户的 [ISocialProfile](isocialprofileisocialperson.md) 接口。  <br/> |
|[GetLogonUrl](isocialsession-getlogonurl.md) <br/> |方法  <br/> |获取一个字符串，代表在 Web 身份验证期间用于向用户显示基于浏览器的表单的 URL。  <br/> |
|[GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) <br/> |方法  <br/> |获取一个字符串，该字符串代表给定社交网络连接的唯一社交网络标识符。  <br/> |
|[GetPerson](isocialsession-getperson.md) <br/> |方法  <br/> |获取基于 _userID_ 参数的 [ISocialPerson](isocialpersoniunknown.md)接口。  <br/> |
|[LoggedOnUserID](isocialsession-loggedonuserid.md) <br/> |属性  <br/> |返回一个字符串，表示当前登录的用户的社交网络用户 ID。  <br/> |
|[LoggedOnUserName](isocialsession-loggedonusername.md) <br/> |属性  <br/> |返回一个字符串，该字符串表示登录时所使用的用户名。  <br/> |
|[登录](isocialsession-logon.md) <br/> |方法  <br/> |使用指定的用户名和密码登录到社交网络网站。  <br/> |
|[LogonWeb](isocialsession-logonweb.md) <br/> |方法  <br/> |使用基于表单的身份验证登录到社交网络网站。  <br/> |
|[SiteUrl](isocialsession-siteurl.md) <br/> |属性  <br/> |设置社交网络网站 URL。  <br/> |
|[UnFollowPerson](isocialsession-unfollowperson.md) <br/> |方法  <br/> |删除  _userID_ 参数标识为社交网络上好友的人。  <br/> |
   
## <a name="remarks"></a>备注

OSC 提供程序必须实现此接口以与 OSC 通信。
  
## <a name="see-also"></a>另请参阅

- [OutlookSocial Connector Provider Interfaces](outlook-social-connector-provider-interfaces.md)

