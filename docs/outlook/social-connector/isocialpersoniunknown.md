---
title: ISocialPerson IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17a2fa12-a7ef-4a95-9875-72ec6f8ceac9
description: 表示社交网络上的人员。
ms.openlocfilehash: 0ad129b0fc15fc9f3ccdf1cff7d8519bb07b024e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331939"
---
# <a name="isocialperson--iunknown"></a>ISocialPerson : IUnknown

表示社交网络上的人员。
  
## <a name="members"></a>Members

下表显示了**ISocialPerson**接口上可用的成员。 
  
|**Name**|**成员类型**|**Description**|
|:-----|:-----|:-----|
|[GetActivities](isocialperson-getactivities.md) <br/> |方法  <br/> |由于 Outlook Social Connector 2013, 此方法已被弃用。  <br/> |
|[GetDetails](isocialperson-getdetails.md) <br/> |方法  <br/> |获取一个字符串, 表示人员的详细信息, 如名字、姓氏和指向个人资料图片的 URL。  <br/> |
|[GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) <br/> |方法  <br/> |获取表示人员集合的字符串。  <br/> |
|[GetFriendsAndColleaguesIDs](isocialperson-getfriendsandcolleaguesids.md) <br/> |方法  <br/> |目前不支持此方法。  <br/> |
|[GetPicture](isocialperson-getpicture.md) <br/> |方法  <br/> |获取包含人员的图片资源的字节数组。  <br/> |
|[GetStatus](isocialperson-getstatus.md) <br/> |方法  <br/> |目前不支持此方法。  <br/> |
   
## <a name="remarks"></a>注解

Outlook Social Connector (.osc) 提供程序必须实现此接口才能与 .osc 通信。
  
## <a name="see-also"></a>另请参阅

- [Outlook Social Connector 提供程序接口](outlook-social-connector-provider-interfaces.md)

