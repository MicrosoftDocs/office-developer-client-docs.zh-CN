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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357363"
---
# <a name="isocialsession--iunknown"></a>ISocialSession : IUnknown

表示与社交网络网站的连接。
  
## <a name="members"></a>Members

下表显示了**ISocialSession**接口上可用的成员。 
  
|**Name**|**成员类型**|**Description**|
|:-----|:-----|:-----|
|[FindPerson](isocialsession-findperson.md) <br/> |方法  <br/> |获取一个字符串, 表示与_userID_参数匹配的一个或多个人员。  <br/> |
|[FollowPerson](isocialsession-followperson.md) <br/> |方法  <br/> |将_emailAddress_参数标识的人员添加为社交网络上已登录用户的友元。  <br/> |
|[GetActivities](isocialsession-getactivities.md) <br/> |方法  <br/> |在 Outlook Social Connector (.osc) 1.1 中已弃用此方法。  <br/> |
|[GetLoggedOnUser](isocialsession-getloggedonuser.md) <br/> |方法  <br/> |获取一个[ISocialProfile](isocialprofileisocialperson.md)接口, 该接口表示已登录的用户。  <br/> |
|[GetLogonUrl](isocialsession-getlogonurl.md) <br/> |方法  <br/> |获取一个字符串, 表示用于在 web 身份验证期间向用户呈现基于浏览器的表单的 URL。  <br/> |
|[GetNetworkIdentifier](isocialsession-getnetworkidentifier.md) <br/> |方法  <br/> |获取一个字符串, 表示给定的社交网络连接的唯一社交网络标识符。  <br/> |
|[GetPerson](isocialsession-getperson.md) <br/> |方法  <br/> |获取基于_userID_参数的[ISocialPerson](isocialpersoniunknown.md)接口。  <br/> |
|[LoggedOnUserID](isocialsession-loggedonuserid.md) <br/> |属性  <br/> |返回一个字符串, 表示当前登录的用户的社交网络用户 ID。  <br/> |
|[LoggedOnUserName](isocialsession-loggedonusername.md) <br/> |属性  <br/> |返回一个字符串, 表示登录时使用的用户名。  <br/> |
|[登录](isocialsession-logon.md) <br/> |方法  <br/> |使用指定的用户名和密码登录到社交网络网站。  <br/> |
|[LogonWeb](isocialsession-logonweb.md) <br/> |方法  <br/> |使用基于表单的身份验证登录到社交网络网站。  <br/> |
|[SiteUrl](isocialsession-siteurl.md) <br/> |属性  <br/> |设置社交网络网站 URL。  <br/> |
|[UnFollowPerson](isocialsession-unfollowperson.md) <br/> |方法  <br/> |删除由_userID_参数标识为社交网络上的友元的人员。  <br/> |
   
## <a name="remarks"></a>注解

一个 .osc 提供程序必须实现此接口才能与 .osc 进行通信。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

