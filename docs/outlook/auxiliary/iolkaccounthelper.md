---
title: IOlkAccountHelper
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fc2972da-80e9-50e2-10b3-585eb63e9103
ms.openlocfilehash: 3c28b1e8ab7e2d72d27cc6545b6ef57834ef5b6f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774326"
---
# <a name="iolkaccounthelper"></a>IOlkAccountHelper

在当前的 MAPI 会话管理帐户中提供的帮助器功能。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkAccountHelper  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[Placeholder1](iolkaccounthelper-placeholder1.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[GetIdentity](iolkaccounthelper-getidentity.md) <br/> |获取帐户的配置文件名称。  <br/> |
|[GetMapiSession](iolkaccounthelper-getmapisession.md) <br/> |打开 MAPI 会话，并为帐户管理器中维护会话的引用。  <br/> |
|[HandsOffSession](iolkaccounthelper-handsoffsession.md) <br/> |释放[IOlkAccountHelper::GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI 会话对象。  <br/> |
   
## <a name="remarks"></a>说明

初始化帐户管理器时，该接口被传递给[IOlkAccountManager::Init](iolkaccountmanager-init.md) 。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

