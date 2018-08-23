---
title: IOlkErrorUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9cfbf12c-a71c-092b-d86a-c5585b0f1edb
ms.openlocfilehash: 311d055e0a319ec26cdc4eba5ac3b50dc9e63d9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565177"
---
# <a name="iolkerrorunknown"></a>IOlkErrorUnknown

提供有关最后一个错误的额外信息。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](https://docs.microsoft.com/en-us/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
|提供者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkErrorUnknown  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iolkerrorunknown-getlasterror.md) <br/> |获取指定的错误消息字符串。  <br/> |
   
## <a name="remarks"></a>注解

此接口提供了有关[IOlkAccountManager](iolkaccountmanager.md)、 [IOlkAccountNotify](iolkaccountnotify.md)和[IOlkAccount](iolkaccount.md)中的错误的额外信息。 它也是**IOlkAccountManager**、 **IOlkAccountNotify**和**IOlkAccount**的基接口。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

