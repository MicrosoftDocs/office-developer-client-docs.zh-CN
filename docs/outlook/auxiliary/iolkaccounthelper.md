---
title: IOlkAccountHelper
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fc2972da-80e9-50e2-10b3-585eb63e9103
ms.openlocfilehash: 241babe45b543fb00c0d2756a2e846303a1717b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322153"
---
# <a name="iolkaccounthelper"></a>IOlkAccountHelper

提供当前 MAPI 会话中的帮助程序功能来管理帐户。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自:  <br/> |[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |客户端  <br/> |
|接口标识符:  <br/> |IID_IOlkAccountHelper  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Placeholder1](iolkaccounthelper-placeholder1.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[GetIdentity](iolkaccounthelper-getidentity.md) <br/> |获取帐户的配置文件名称。  <br/> |
|[GetMapiSession](iolkaccounthelper-getmapisession.md) <br/> |打开 MAPI 会话并维护对帐户管理员会话的引用。  <br/> |
|[HandsOffSession](iolkaccounthelper-handsoffsession.md) <br/> |释放[IOlkAccountHelper:: GetMapiSession](iolkaccounthelper-getmapisession.md)返回的 MAPI session 对象。  <br/> |
   
## <a name="remarks"></a>注解

初始化帐户管理器时, 此接口将传递给[IOlkAccountManager:: Init](iolkaccountmanager-init.md) 。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

