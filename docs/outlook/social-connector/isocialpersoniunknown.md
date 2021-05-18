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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407009"
---
# <a name="isocialperson--iunknown"></a>ISocialPerson : IUnknown

表示社交网络上的人员。
  
## <a name="members"></a>Members

下表显示了 **ISocialPerson 接口上可用的** 成员。 
  
|**名称**|**成员类型**|**说明**|
|:-----|:-----|:-----|
|[GetActivities](isocialperson-getactivities.md) <br/> |方法  <br/> |自 Social Connector 2013 Outlook已弃用此方法。  <br/> |
|[GetDetails](isocialperson-getdetails.md) <br/> |方法  <br/> |获取一个字符串，代表人员的详细信息，例如名字、姓氏和个人资料图片的 URL。  <br/> |
|[GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md) <br/> |方法  <br/> |获取一个代表人员集合的字符串。  <br/> |
|[GetFriendsAndColleaguesIDs](isocialperson-getfriendsandcolleaguesids.md) <br/> |方法  <br/> |此方法当前不受支持。  <br/> |
|[GetPicture](isocialperson-getpicture.md) <br/> |方法  <br/> |获取包含人员的图片资源的字节数组。  <br/> |
|[GetStatus](isocialperson-getstatus.md) <br/> |方法  <br/> |此方法当前不受支持。  <br/> |
   
## <a name="remarks"></a>备注

OSC Outlook的 (连接器) 必须实现此接口以与 OSC 通信。
  
## <a name="see-also"></a>另请参阅

- [OutlookSocial Connector Provider Interfaces](outlook-social-connector-provider-interfaces.md)

