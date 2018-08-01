---
title: IOlkErrorUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9cfbf12c-a71c-092b-d86a-c5585b0f1edb
ms.openlocfilehash: 3e0504ecb70362e84360c6cc9962fea5b8f470a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774356"
---
# <a name="iolkerrorunknown"></a>IOlkErrorUnknown

提供有关最后一个错误的额外信息。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](http://msdn.microsoft.com/library/com.iunknown%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkErrorUnknown  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iolkerrorunknown-getlasterror.md) <br/> |获取指定的错误消息字符串。  <br/> |
   
## <a name="remarks"></a>说明

此接口提供了有关[IOlkAccountManager](iolkaccountmanager.md)、 [IOlkAccountNotify](iolkaccountnotify.md)和[IOlkAccount](iolkaccount.md)中的错误的额外信息。 它也是**IOlkAccountManager**、 **IOlkAccountNotify**和**IOlkAccount**的基接口。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

