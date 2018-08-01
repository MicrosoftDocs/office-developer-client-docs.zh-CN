---
title: IOlkAccountHelperHandsOffSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9f71fdef-5df5-0892-b64c-293a2f22f5c3
description: 释放 IOlkAccountHelper::GetMapiSession 返回的 MAPI 会话对象。
ms.openlocfilehash: 71931be73e75e858224d3da2c92071341ac45e72
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774327"
---
# <a name="iolkaccounthelperhandsoffsession"></a>IOlkAccountHelper::HandsOffSession

释放由- [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI 会话对象。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkAccountHelper](iolkaccounthelper.md)。
  
```cpp
HRESULT IOlkAccountHelper::HandsOffSession( );
```

## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |如果您的实现的**IOlkAccountHelper**创建**IOlkAccountHelper::GetMapiSession**返回自己 MAPI 会话，必须释放此处会话并返回 S_OK。  <br/> |
|E_NOTIMPL  <br/> |如果您的实现的**IOlkAccountHelper**没有创建自己的 MAPI 会话，您必须返回仅 E_NOTIMPL。 在这种情况下，这是唯一受支持的返回值。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md)

