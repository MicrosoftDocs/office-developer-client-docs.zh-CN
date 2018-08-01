---
title: ISocialSessionUnFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66c83041-ee83-41d5-b9dc-a4dc4c670f82
description: 删除为社交网络上朋友 userID 参数标识的人员。
ms.openlocfilehash: 8b9a1e4f903e4bc805481b8679481103ea1ec82c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779242"
---
# <a name="isocialsessionunfollowperson"></a>ISocialSession::UnFollowPerson

删除为社交网络上朋友_userID_参数标识的人员。 
  
```cpp
HRESULT _stdcall UnFollowPerson([in] BSTR userID);
```

## <a name="parameters"></a>参数

_用户 Id_
  
> [in]一个字符串，包含社交网络用户 ID 的人员。
    
## <a name="remarks"></a>说明

_UserID_参数必须为有效的用户 ID 的社交网络上的人员。 
  
如果 Outlook Social Connector (OSC) 提供程序已设为**true** **功能**的 XML **doNotFollowPerson** ，提供程序必须在的用户中传递 ID 不匹配网络上的用户的情况下返回 OSC_E_NOT_FOUND 错误。 如果提供程序已将**doNotFollowPerson**设置为**false** ，在**功能**中，提供程序应返回 OSC_E_FAIL 错误。 有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

