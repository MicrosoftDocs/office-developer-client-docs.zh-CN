---
title: IOlkEnum
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 33cb89cb-c967-760c-6bc4-94118a4f872c
ms.openlocfilehash: 59f43e8b3b0819b0178d60fa357e01937ae19d81
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322097"
---
# <a name="iolkenum"></a>IOlkEnum

支持将帐户枚举为 [IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) 对象。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自：  <br/> |[IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
|实现者：  <br/> |Outlook  <br/> |
|提供者：  <br/> |[IOlkAccountManager::EnumerateAccounts](iolkaccountmanager-enumerateaccounts.md) <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkEnum  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetCount](iolkenum-getcount.md) <br/> |获取枚举器中的帐户数。  <br/> |
|[Reset](iolkenum-reset.md) <br/> |将枚举器重置为开头。  <br/> |
|[GetNext](iolkenum-getnext.md) <br/> |获取枚举器中的下一个帐户。  <br/> |
|[Skip](iolkenum-skip.md) <br/> |跳过枚举器中的指定数目的帐户。  <br/> |
   
## <a name="remarks"></a>备注

获取帐户的枚举器时 **，IOlkAccountManager：：EnumerateAccounts** 将返回此接口。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

