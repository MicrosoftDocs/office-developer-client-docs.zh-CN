---
title: IOlkAccountHelperHandsOffSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9f71fdef-5df5-0892-b64c-293a2f22f5c3
description: '释放 IOlkAccountHelper:: GetMapiSession 返回的 MAPI session 对象。'
ms.openlocfilehash: c481cee1ecb8c2bd3997cdee8ae86c9c3b5a712e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418629"
---
# <a name="iolkaccounthelperhandsoffsession"></a>IOlkAccountHelper::HandsOffSession

释放由- [IOlkAccountHelper:: GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI 会话对象。
  
## <a name="quick-info"></a>快速信息

请参阅[IOlkAccountHelper](iolkaccounthelper.md)。
  
```cpp
HRESULT IOlkAccountHelper::HandsOffSession( );
```

## <a name="return-values"></a>返回值

|**[HRESULT]**|**说明**|
|:-----|:-----|
|S_OK  <br/> |如果您的**IOlkAccountHelper**实现创建其自己的在**IOlkAccountHelper:: GetMapiSession**中返回的 MAPI 会话, 则必须在此处发布会话并返回 S_OK。  <br/> |
|E_NOTIMPL  <br/> |如果您的**IOlkAccountHelper**实现没有创建自己的 MAPI 会话, 则必须仅返回 E_NOTIMPL。 在这种情况下, 这是唯一受支持的返回值。  <br/> |
   
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)  
- [IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md)

