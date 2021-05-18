---
title: ISocialSession2 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f516e86e-0158-472b-9711-fe7491b24404
description: 支持添加好友、按需或好友混合同步、按需同步活动，或者使用缓存凭据登录社交网络。
ms.openlocfilehash: 6dc581bb812408d7e01f94c375671783445616a1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408829"
---
# <a name="isocialsession2--iunknown"></a>ISocialSession2 : IUnknown

支持添加好友、按需或好友混合同步、按需同步活动，或者使用缓存凭据登录社交网络。
  
## <a name="members"></a>Members

下表显示了 **ISocialSession2** 接口上可用的成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[FollowPersonEx](isocialsession2-followpersonex.md) <br/> |方法  <br/> |将  _emailAddresses_ 和  _displayName_ 参数标识的人添加为社交网络上登录的用户的好友。  <br/> |
|[GetActivitiesEx](isocialsession2-getactivitiesex.md) <br/> |方法  <br/> |获取一个字符串，该字符串代表  _hashedAddresses_ 参数指定的用户的活动集合。  <br/> |
|[GetPeopleDetails](isocialsession2-getpeopledetails.md) <br/> |方法  <br/> |返回一个字符串，其中包含  _personAddresses_ 参数指定的用户的人员和图片详细信息的集合。  <br/> |
|[LogonCached](isocialsession2-logoncached.md) <br/> |方法  <br/> |使用缓存的凭据登录到社交网络网站。  <br/> |
   
## <a name="remarks"></a>备注

如果 Outlook Social Connector (OSC) 提供程序支持好友的按需或混合同步、活动的按需同步，或者使用缓存的凭据登录到社交网络，则提供商可以选择实现此接口。 如果 OSC 提供程序实现 **ISocialSession2** 并支持在社交网络上关注人员，则 OSC 将调用 [ISocialSession2：：FollowPersonEx](isocialsession2-followpersonex.md)而不是 [ISocialSession：：FollowPerson，](isocialsession-followperson.md)并且该提供程序也必须实现 **ISocialSession2：：FollowPersonEx。**
  
## <a name="see-also"></a>另请参阅

- [OutlookSocial Connector Provider Interfaces](outlook-social-connector-provider-interfaces.md)

