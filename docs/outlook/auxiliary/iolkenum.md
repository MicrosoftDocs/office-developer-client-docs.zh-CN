---
title: IOlkEnum
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 33cb89cb-c967-760c-6bc4-94118a4f872c
ms.openlocfilehash: 59f43e8b3b0819b0178d60fa357e01937ae19d81
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389734"
---
# <a name="iolkenum"></a>IOlkEnum

支持枚举作为[IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown)对象的帐户。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) <br/> |
|实现者：  <br/> |Outlook  <br/> |
|提供者：  <br/> |[IOlkAccountManager::EnumerateAccounts](iolkaccountmanager-enumerateaccounts.md) <br/> |
|调用者：  <br/> |客户端  <br/> |
|接口标识符：  <br/> |IID_IOlkEnum  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[GetCount](iolkenum-getcount.md) <br/> |获取枚举中的帐户数。  <br/> |
|[Reset](iolkenum-reset.md) <br/> |重将枚举器重置到开头。  <br/> |
|[GetNext](iolkenum-getnext.md) <br/> |获取枚举中的下一个帐户。  <br/> |
|[跳过](iolkenum-skip.md) <br/> |跳过指定的数量的枚举中的帐户。  <br/> |
   
## <a name="remarks"></a>说明

此接口返回**IOlkAccountManager::EnumerateAccounts**时获取帐户的枚举。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md) 
- [常量 （帐户管理 API）](constants-account-management-api.md)

