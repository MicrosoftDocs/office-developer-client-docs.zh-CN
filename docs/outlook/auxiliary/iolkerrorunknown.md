---
title: IOlkErrorUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9cfbf12c-a71c-092b-d86a-c5585b0f1edb
ms.openlocfilehash: dc2fe6bbaf4515d5c5f5be694b15040bf03ef374
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384638"
---
# <a name="iolkerrorunknown"></a>IOlkErrorUnknown

提供有关最后一个错误的额外信息。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
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

