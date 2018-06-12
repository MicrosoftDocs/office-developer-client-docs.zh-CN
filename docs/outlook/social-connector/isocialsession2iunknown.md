---
title: ISocialSession2 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f516e86e-0158-472b-9711-fe7491b24404
description: 支持使用缓存的凭据添加朋友、 按需或混合同步朋友、 活动或登录到社交网络的按需同步。
ms.openlocfilehash: b14804d35e54ebe9fe2a529fb2664f0a661653bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779245"
---
# <a name="isocialsession2--iunknown"></a>ISocialSession2: IUnknown

支持使用缓存的凭据添加朋友、 按需或混合同步朋友、 活动或登录到社交网络的按需同步。
  
## <a name="members"></a>成员

下表显示了**ISocialSession2**接口上可用的成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[FollowPersonEx](isocialsession2-followpersonex.md) <br/> |方法  <br/> |添加为社交网络登录用户的朋友由_emailAddresses_和_displayName_参数标识的人员。  <br/> |
|[GetActivitiesEx](isocialsession2-getactivitiesex.md) <br/> |方法  <br/> |获取一个字符串，表示活动_hashedAddresses_参数指定的用户的集合。  <br/> |
|[GetPeopleDetails](isocialsession2-getpeopledetails.md) <br/> |方法  <br/> |返回一个字符串，包含一人和图片_personsAddresses_参数指定用户的详细信息。  <br/> |
|[LogonCached](isocialsession2-logoncached.md) <br/> |方法  <br/> |登录到使用缓存的凭据的社交网络站点。  <br/> |
   
## <a name="remarks"></a>备注

Outlook Social Connector (OSC) 提供程序可以选择实现此接口，如果提供程序支持的点播或混合同步朋友、 活动或登录到社交网络的按需同步使用缓存的凭据。 如果 OSC 提供程序实现**ISocialSession2**和支持以下社交网络上的人员，OSC 调用[ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md)而不是[ISocialSession::FollowPerson](isocialsession-followperson.md)，并提供程序必须实现**ISocialSession2::FollowPersonEx**，以及。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

